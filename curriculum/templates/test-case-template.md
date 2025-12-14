# Test Case Template

> **Note:** This template aligns with Week 8 GitHub Projects test management. Use this for markdown files and the GitHub Issue Template for creating test case issues.

---

## Test Case Information

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-[MODULE]-[###] (e.g., TC-LOGIN-001, TC-CART-015) |
| **Test Case Title** | Clear, concise title describing what is being tested |
| **Module** | Login / Inventory / Cart / Checkout / User Account / Navigation |
| **Test Type** | UI / API / E2E / Regression / Smoke / Integration / Performance |
| **Test Suite** | Regression / Smoke / Full / Sanity / Exploratory |
| **Severity** | S0-Blocker / S1-Critical / S2-Major / S3-Minor / S4-Trivial |
| **Automation Status** | Not Automated / In Progress / Automated |
| **Created By** | Your name |
| **Created Date** | YYYY-MM-DD |
| **Last Updated** | YYYY-MM-DD |

---

## Severity Guidelines

| Level | Definition | Example |
|-------|------------|---------|
| **S0 - Blocker** | Can't test, blocks release | Login completely broken, app won't load |
| **S1 - Critical** | Production down, data loss, security flaw | Checkout fails for all users, payment not processing |
| **S2 - Major** | Key feature broken, significant impact | Search not working, cart total incorrect |
| **S3 - Minor** | Edge case, workaround exists | Sorting fails for specific filter combination |
| **S4 - Trivial** | Cosmetic, polish, minor UI | Button color slightly off, typo in tooltip |

---

## Test Type Definitions

| Type | Purpose | Example |
|------|---------|---------|
| **UI** | User interface validation | Verify login button is enabled |
| **API** | Backend service testing | Verify POST /cart/add returns 200 |
| **E2E** | End-to-end user journey | Login → Add to cart → Checkout → Complete |
| **Regression** | Prevent old bugs from returning | Re-test fixed bug scenarios |
| **Smoke** | Critical path validation | Basic login and checkout work |
| **Integration** | Component interaction | Cart updates when inventory changes |
| **Performance** | Speed and responsiveness | Page loads in <2 seconds |

---

## Test Objective

Brief description of what this test case validates (1-2 sentences).

**Example:**
> To verify that a user with valid credentials (standard_user) can successfully log in to the SauceDemo application and is redirected to the inventory page.

---

## Preconditions

List all conditions that must be met before executing this test:
- SauceDemo application is accessible
- Test user account exists: standard_user / secret_sauce
- No active session (user logged out or cleared cookies)
- Browser: Chrome latest version

---

## Test Data

| Data Field | Value | Notes |
|------------|-------|-------|
| Username | standard_user | Valid user from SauceDemo |
| Password | secret_sauce | Correct password |
| Expected URL | https://www.saucedemo.com/inventory.html | Post-login redirect |

---

## Test Steps & Expected Results

| Step # | Action | Expected Result | Actual Result | Status |
|--------|--------|-----------------|---------------|--------|
| 1 | Navigate to https://www.saucedemo.com/ | Login page displays with username, password fields, LOGIN button | | |
| 2 | Enter "standard_user" in Username field | Text "standard_user" appears in field | | |
| 3 | Enter "secret_sauce" in Password field | Password appears masked (dots) | | |
| 4 | Click LOGIN button | User redirected to /inventory.html, 6 products visible | | |

---

## Execution Results

### Last Run Status

- [ ] Not Run
- [ ] Pass
- [ ] Fail
- [ ] Blocked
- [ ] Skipped

### Execution Details

| Field | Value |
|-------|-------|
| **Executed By** | [Tester Name] |
| **Execution Date** | YYYY-MM-DD |
| **Execution Time** | [Duration in minutes] |
| **Build/Version** | [App version tested] |

---

## Test Environment

| Component | Details |
|-----------|---------|
| **OS** | Windows 11 / macOS Sonoma / Ubuntu 22.04 |
| **Browser** | Chrome 120+ / Firefox 120+ / Safari 17+ / Edge 120+ |
| **Screen Resolution** | 1920×1080 / 1366×768 |
| **Application URL** | https://www.saucedemo.com/ |
| **Test Environment** | Production / Staging / QA |

---

## Requirements Traceability

| Requirement ID | Requirement Description |
|----------------|-------------------------|
| REQ-AUTH-001 | User must be able to log in with valid credentials |
| REQ-AUTH-002 | User must be redirected to inventory page after successful login |

**Coverage:** This test validates REQ-AUTH-001 and REQ-AUTH-002

---

## Test Independence

**Important:** This test case must be **independent** and **not depend on other test cases**.

✅ **Good - Independent:**
```markdown
Preconditions:
- User is on login page
- No active session
```

❌ **Bad - Dependent:**
```markdown
Preconditions:
- TC-LOGIN-001 must pass first
- Depends on: TC-SETUP-005
```

**Why:** If TC-LOGIN-001 fails, this test gets blocked. Always set up required state in preconditions, don't reference other tests.

---

## Linked Defects

If test fails, link to bug reports:

| Defect ID | Defect Title | Severity | Status |
|-----------|--------------|----------|--------|
| BUG-045 | Login fails with special characters | S2-Major | Open |

---

## Notes / Comments

Any additional information, observations, or special considerations:
- This is a smoke test - must pass before further testing
- Test executes in ~30 seconds
- Known issue: Slow on Firefox (performance issue tracked in BUG-089)

---

## GitHub Projects Integration

When creating this test case as a GitHub issue:

1. **Use GitHub Issue Template:** `.github/ISSUE_TEMPLATE/02-test-case.yml`
2. **Add labels:**
   - Test type: `test:ui`, `test:api`, `test:e2e`, `test:regression`, `test:smoke`, `test:integration`, `test:performance`
   - Severity: `severity:s0-blocker`, `severity:s1-critical`, `severity:s2-major`, `severity:s3-minor`, `severity:s4-trivial`
3. **Add to Project:** "SauceDemo Test Suite"
4. **Set custom fields:**
   - Test Type: [Select from dropdown]
   - Test Suite: [Select from dropdown]
   - Severity: [Auto-populated from labels]
   - Module: [Select from dropdown]
   - Automation Status: Not Automated
   - Last Run Status: Not Run

---

## Best Practices

### ✅ DO:
- Use specific, measurable expected results
- Number steps sequentially
- One action per step
- Include exact values (not "some value")
- Make test independent (no dependencies)
- Use consistent naming (TC-MODULE-###)
- Update status after execution
- Link to requirements

### ❌ DON'T:
- Use vague steps ("test login")
- Combine multiple actions per step
- Make tests dependent on other tests
- Use placeholder data ("enter valid username")
- Skip expected results
- Forget to update traceability
- Reuse test case IDs

---

**Template Version:** 2.0 (FAANG-Level, aligned with GitHub Projects)
**Last Updated:** December 2025
**Compatible With:** Week 8 Test Case Management, GitHub Projects v1.2.0
