# Week 06 — Pairwise Testing

## Objective

Create pairwise combinations for SauceDemo testing.

## Parameters

**User Type:** `standard_user`, `problem_user`, `performance_glitch_user`
**Sort Order:** Name (A–Z), Name (Z–A), Price (low→high), Price (high→low)
**Cart Status:** Empty, Has items

## Pairwise Test Cases

| Test | User Type               | Sort Order       | Cart Status | Expected Result                       |
| ---- | ----------------------- | ---------------- | ----------- | ------------------------------------- |
| 1    | standard_user           | Name (A–Z)       | Empty       | Backpack appears first                |
| 2    | standard_user           | Price (high→low) | Has items   | Jacket appears first                  |
| 3    | problem_user            | Name (Z–A)       | Empty       | T-Shirt (Red) appears first           |
| 4    | problem_user            | Price (low→high) | Has items   | Onesie appears first                  |
| 5    | performance_glitch_user | Name (A–Z)       | Has items   | Backpack first (slower load expected) |
| 6    | performance_glitch_user | Price (high→low) | Empty       | Jacket first (slower load expected)   |

## Instructions for Execution

1. Navigate to [https://www.saucedemo.com](https://www.saucedemo.com)
2. Log in with the User Type from the test row
3. If `Cart Status = Has items`, add any product to cart
4. Apply the Sort Order specified
5. Verify the first product displayed matches the Expected Result

## Notes

* Ensures all parameter pairs are covered at least once
* High-risk combinations manually included
* Pairwise reduces total test cases from 24 → 6
* Can supplement with additional edge cases if necessary

