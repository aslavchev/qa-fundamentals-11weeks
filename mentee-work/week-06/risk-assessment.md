# Week 06 — Exercise 3: Risk Assessment

## Objective

Identify and prioritize risks in SauceDemo features, and allocate testing effort proportionally using a risk-based approach.

## Steps

1. **List Features and Components**

   * Login authentication
   * Add to cart
   * Remove from cart
   * Product sort
   * Checkout process
   * Product images
   * Footer links

2. **Assess Likelihood and Impact**

   * **Likelihood:** probability of failure (High / Medium / Low)
   * **Impact:** consequence if failure occurs (High / Medium / Low)
   * **Risk Level:** Likelihood × Impact (assign numeric score, e.g., High=3, Medium=2, Low=1)

3. **Create Risk Assessment Table**
   | Feature                | Likelihood | Impact | Risk Score | Risk Level | Recommended Test Approach |
   |------------------------|------------|--------|------------|------------|---------------------------|
   | Login authentication   | High       | High   | 9          | 🔴 Critical | 25+ test cases, security testing, automation |
   | Add to cart            | Medium     | High   | 6          | 🟠 High     | 15 test cases, state and boundary testing |
   | Remove from cart       | Low        | Medium | 2          | 🟡 Medium   | 5 test cases, exploratory verification |
   | Product sort           | Medium     | Medium | 4          | 🟡 Medium   | 8 test cases, visual verification |
   | Checkout process       | High       | High   | 9          | 🔴 Critical | 30+ test cases, E2E automation |
   | Product images         | Low        | Low    | 1          | 🟢 Low      | Visual inspection only |
   | Footer links           | Low        | Low    | 1          | 🟢 Low      | Quick smoke test |

4. **Prioritize Testing**

   * High risk → extensive testing: formal techniques + automation
   * Medium risk → moderate testing: combination of formal and exploratory
   * Low risk → minimal testing: smoke tests, visual checks, happy path

5. **Mitigation & Communication**

   * Document rationale for all risk scores
   * Share assessment with stakeholders
   * Update risk matrix after major changes or new releases
   * Track whether high-risk areas produce more defects (validate prioritization)

