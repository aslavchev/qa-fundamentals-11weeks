# Test Coverage Analysis — Week 06

## 1. Purpose

The goal of this analysis is to review the current test coverage of SauceDemo, identify gaps, and recommend improvements using a layered testing strategy (risk-based testing, formal techniques, exploratory testing, and coverage measurement).

## 2. Current Coverage Overview

Up to Week 6, testing includes:

Login tests
Inventory and sorting tests
Cart functionality tests
Checkout flow (all three steps)
Pairwise tests for user types and sorting
Exploratory sessions for cart and checkout

Based on these, estimated coverage is around **75%**.

## 3. Coverage by Feature Area

### Login

Most positive and negative flows tested (valid user, locked user, invalid password).
Gap: No session-expiration tests.

### Inventory & Sorting

Covered basic sorting options and product visibility.
Gap: No testing for broken images or browser compatibility.

### Cart

Covered add/remove functionality.
Gap: No tests for quantity changes (feature missing) and no cross-browser cart persistence testing.

### Checkout

Covered form validation and normal flow.
Gaps:
Data consistency after Back navigation
Mobile behavior
Multiple rapid submissions

### Order Completion

Complete order flow tested.
Gap: No tests for repeated Finish action or session timeout.

## 4. Risk Assessment

Critical: Login, Checkout
High: Cart operations
Medium: Sorting, product details
Low: Social links, footer elements

High-risk areas have good coverage, but some behaviors (Back button, multi-step state issues) still need testing.

## 5. Missing Test Areas (Gaps)

1. Session and state tests (Back button behavior, multi-tab usage).
2. Mobile UI coverage across Inventory, Cart, and Checkout.
3. Slow network and throttling tests.
4. Browser compatibility (Firefox, Edge, Safari).
5. Checkout data refresh issues (Overview page not updating).
6. Order completion idempotency (Finish button multiple actions).
7. Image loading and broken assets on Inventory page.

## 6. Recommended New Tests

Add around **10 new tests**, including:

1. Back button behavior during checkout
2. Multiple Finish attempts after order completion
3. Mobile cart badge tests
4. Slow-network checkout test
5. Cross-browser inventory loading
6. Multi-tab cart state persistence
7. Handling of expired session during checkout
8. Product image loading validation
9. Checkout form auto-fill behavior
10. Sorting consistency across browsers

These additions should raise coverage closer to **90%**.

## 7. Summary

The current test suite covers the main user flows well but has several important gaps related to state handling, mobile behavior, browser compatibility, and edge cases. By adding roughly 10 targeted tests, coverage can improve from approximately **75% to 90%**, increasing confidence in overall product quality.
