# Exploratory Testing Session — Week 06

## Session Charter

Explore the main user flow (Login → Inventory → Cart → Checkout) using standard_user and Chrome DevTools in order to find UI issues, inconsistent behavior, and problems related to navigation and validation.

## Session Notes (Timeline)

### 00:00–00:15 — Login and Inventory

Login works as expected. The inventory page displays six products. The default sorting option says "Name (A to Z)" but the product order does not appear fully correct.

### 00:15–00:30 — Add to Cart

Adding and removing items works. In mobile view, the cart badge overlaps the cart icon, which affects visibility.

### 00:30–00:45 — Cart Page

All added items are displayed correctly. There is no option to change product quantity. Removing an item happens immediately without any confirmation step.

### 00:45–01:00 — Checkout Step One

Form validation works correctly for empty fields and partial inputs. Special characters are displayed as plain text, which means they are sanitized.

### 01:00–01:15 — Checkout Overview

The overview page loads the correct information. When using the browser Back button, updating the user information and returning to the overview does not refresh the displayed data.

### 01:15–01:30 — Order Completion

The Finish button completes the order and displays the final page. Navigating back allows the Finish button to be clicked again, which should not be possible.

## Bugs Found

1. Incorrect default product sorting on the inventory page (Medium severity)
2. Cart badge overlaps the cart icon in mobile view (Low severity)
3. User information does not update on the overview page after using Back and editing the form (High severity)
4. The Finish action can be triggered more than once after using Back navigation (Medium severity)

## Usability Issues

There is no way to change quantities in the cart.
Item removal happens without confirmation.
Shipping information on the checkout pages is hardcoded.

## Future Test Ideas

Test under slow network conditions.
Check behavior in additional browsers.
Explore multi-tab sessions and state handling.

## Summary

This 90-minute exploratory session found several UI and state-related issues, especially in the checkout process. Core functionality works, but navigation and consistency problems can affect the user experience.
