# Week 06 — Exercise 2: Error Guessing

## Objective

Predict likely failures in SauceDemo using the experience-based Error Guessing technique.

## SauceDemo Example Error Guesses

### Login Issues

| Test Case | Input / Action                                  | Expected / Observation          |
| --------- | ----------------------------------------------- | ------------------------------- |
| EG-1      | Empty username & password                       | Error: required fields          |
| EG-2      | Valid username & empty password                 | Error: password required        |
| EG-3      | Spaces before/after username                    | Check if trimmed or login fails |
| EG-4      | Copy-paste username with hidden chars           | Should fail login               |
| EG-5      | Password with special chars (`secret_sauce!@#`) | Login success/failure behavior  |
| EG-6      | SQL Injection: `' OR '1'='1`                    | Should be rejected              |
| EG-7      | XSS attempt: `<script>alert('test')</script>`   | No alert; input sanitized       |
| EG-8      | Very long username (1000+ chars)                | Check for truncation or crash   |
| EG-9      | Username in different case (`STANDARD_USER`)    | Case sensitivity tested         |
| EG-10     | Multiple failed logins                          | Account lockout behavior        |

### Cart Issues

| Test Case | Input / Action                        | Expected / Observation             |
| --------- | ------------------------------------- | ---------------------------------- |
| EG-11     | Add same item 100 times               | Cart handles quantity correctly    |
| EG-12     | Add item → remove cookies → refresh   | Cart state resets appropriately    |
| EG-13     | Add to cart from multiple tabs        | Cart updates correctly             |
| EG-14     | Remove item not in cart via URL       | Should handle gracefully           |
| EG-15     | Checkout with empty cart              | Validation prevents checkout       |
| EG-16     | Negative quantity via inspect element | Should reject invalid quantity     |
| EG-17     | Cart session timeout during checkout  | Checkout fails or session restored |

### Checkout Issues

| Test Case | Input / Action                              | Expected / Observation               |
| --------- | ------------------------------------------- | ------------------------------------ |
| EG-18     | First name: `<script>alert('xss')</script>` | Input sanitized; no JS execution     |
| EG-19     | Zip code: `9999999999999999999`             | Validation rejects                   |
| EG-20     | Zip code: `-12345`                          | Validation rejects                   |
| EG-21     | Last name: `O'Brien`                        | Check proper handling of apostrophes |
| EG-22     | Missing required fields (disable JS)        | Validation enforced server-side      |
| EG-23     | Back button after order placement           | Order not repeated incorrectly       |
| EG-24     | Submit form twice rapidly                   | Only one order processed             |

