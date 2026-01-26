# Week 10 - Exercise 1: Find Bugs in SauceDemo

**Name:** Kamen Asenov  
**Date:** 2026-01-18  
**Total Bugs Found:** 10

---

## Testing Summary

**Testing Duration:** ~1.5–2 hours  
**Modules Tested:** Login, Products, Cart, Checkout, Cross-cutting  
**Users Tested:** standard_user, problem_user, performance_glitch_user  
**Browsers Tested:** Chrome (latest)  
**Tools:** Chrome DevTools (Console, Device Toolbar)

---

## Bug Discovery Log

### BUG-001: Checkout step pages accessible directly (empty-cart checkout possible)
- **Module:** Checkout / Security / State management
- **Discovered via:** Direct URL access testing to checkout pages with empty cart
- **Reproducible:** Yes (5/5 attempts)
- **Affects user(s):** standard_user (likely all authenticated users)
- **Quick notes:** Accessing `checkout-step-one.html` directly allows entering checkout flow without items in cart.

### BUG-002: Zip/Postal Code accepts letters (no format validation)
- **Module:** Checkout
- **Discovered via:** Input validation testing in checkout form
- **Reproducible:** Yes (5/5 attempts)
- **Affects user(s):** standard_user
- **Quick notes:** Zip accepts `ABCDE` and allows continuing to overview without error.

### BUG-003: Remove item has no confirmation/undo
- **Module:** Cart
- **Discovered via:** Usability check while removing items from cart page
- **Reproducible:** Yes (5/5 attempts)
- **Affects user(s):** standard_user (likely all users)
- **Quick notes:** Clicking Remove instantly removes the item; no confirmation or undo option.

### BUG-004: Sort dropdown label does not match initial product order
- **Module:** Products / Sorting
- **Discovered via:** Checking default sort label vs visible list order after login
- **Reproducible:** Intermittent (3/5 attempts)
- **Affects user(s):** standard_user
- **Quick notes:** Dropdown shows “Name (A to Z)” but visible list order on initial load does not clearly reflect strict A→Z ordering.

### BUG-005: Cart badge overlaps icon on mobile viewport
- **Module:** Cart / UI
- **Discovered via:** Responsive UI testing using Device Toolbar
- **Reproducible:** Yes (5/5 attempts)
- **Affects user(s):** standard_user (mobile viewport)
- **Quick notes:** Badge overlaps cart icon on small viewport (e.g., iPhone 12).

### BUG-006: problem_user product images are incorrect/mismatched
- **Module:** Products
- **Discovered via:** Special user testing (problem_user)
- **Reproducible:** Yes (5/5 attempts)
- **Affects user(s):** problem_user
- **Quick notes:** One or more product images do not match their product titles.

### BUG-007: Browser Back after completion may allow re-triggering finish flow
- **Module:** Checkout / Completion
- **Discovered via:** Browser navigation/state testing after completing checkout
- **Reproducible:** Intermittent (3/5 attempts)
- **Affects user(s):** standard_user
- **Quick notes:** After finishing an order, Back may allow re-entering earlier checkout pages (state/idempotency risk).

### BUG-008: Login error message persists while user edits inputs
- **Module:** Login
- **Discovered via:** Negative login test, then editing credentials without resubmitting
- **Reproducible:** Yes (5/5 attempts)
- **Affects user(s):** all users
- **Quick notes:** Error message remains visible while editing username/password fields.

### BUG-009: performance_glitch_user login takes very long with no loading feedback
- **Module:** Login / Performance
- **Discovered via:** Special user testing (performance_glitch_user)
- **Reproducible:** Yes (5/5 attempts)
- **Affects user(s):** performance_glitch_user
- **Quick notes:** Login is noticeably slow, no spinner/loading feedback, button not clearly disabled.

### BUG-010: Keyboard accessibility – focus indication is unclear on key controls
- **Module:** Cross-cutting / Accessibility
- **Discovered via:** Keyboard-only navigation (Tab/Shift+Tab) on inventory page
- **Reproducible:** Intermittent (3/5 attempts)
- **Affects user(s):** keyboard-only users
- **Quick notes:** Focus indicator is weak/inconsistent on some interactive elements (header controls/buttons).

---

## Security Testing Performed

- **SQL Injection (Login):** Tried username payload `' OR '1'='1` with any password → **No vulnerability observed** (application returns standard login error and does not authenticate).
- **XSS (Checkout):** Tried payload `<script>alert(1)</script>` in First Name / Last Name fields → **No vulnerability observed** (no script executed; input appears treated as text / sanitized).

---

## Testing Notes

**Modules with most bugs:** Checkout (3)  
**Most common bug type:** UX/State management (navigation, UI consistency, validation)

**Hardest bug to find:** BUG-007  
- Needed multiple attempts and specific navigation timing.

**Easiest bug to find:** BUG-002  
- Straightforward validation check with obvious outcome.

**What I learned:**
- Direct URL access and Back/Refresh behavior often reveal state bugs.
- Special users are valuable for uncovering non-happy-path behaviors.
- Even when security tests don’t find vulnerabilities, documenting them shows coverage.
