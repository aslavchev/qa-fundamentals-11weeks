# Week 8: Test Case Design & Management - Checklist

## 📋 Weekly Goals
- [ ] Master test case design fundamentals
- [ ] Create 50+ professional test cases for SauceDemo
- [ ] Build Requirements Traceability Matrix with 100% coverage
- [ ] Configure GitHub Projects for test management
- [ ] Apply to SauceDemo systematically

---

## 📚 Tutorial Completion
- [ ] Read complete tutorial.md (2-3 hours)
- [ ] Study Section 1: Anatomy of a Good Test Case (12 components)
- [ ] Study Section 2: Test Design Techniques Applied (EP, BVA, Decision Tables, State Transitions)
- [ ] Study Section 4: Requirements Traceability Matrix (RTM)
- [ ] Study Section 6: Test Case Review & Quality Checklist
- [ ] Review all 3 complete test case examples (Smoke, Negative, Boundary)
- [ ] Answer self-assessment questions at end of tutorial

---

## 🧪 Exercises Completion

### Exercise 1: Write 50+ Test Cases (180 min)
- [ ] Login/Authentication module: 15 test cases created
  - [ ] Positive tests (valid users)
  - [ ] Negative tests (invalid credentials, empty fields)
  - [ ] Security tests (SQL injection)
  - [ ] State tests (logged in/out)
- [ ] Products/Inventory module: 10 test cases created
  - [ ] Product display tests
  - [ ] Sorting tests (name, price)
- [ ] Shopping Cart module: 15 test cases created
  - [ ] Add/remove tests
  - [ ] Cart badge tests
  - [ ] Cart total calculation tests
  - [ ] State transition tests (empty → has items → checkout)
- [ ] Checkout module: 20 test cases created
  - [ ] Form validation tests (decision tables)
  - [ ] Boundary tests (field lengths)
  - [ ] End-to-end smoke test
- [ ] All test cases follow template format (ID, title, module, type, severity, objective, preconditions, steps, expected results)
- [ ] TC-[MODULE]-[###] naming convention used consistently
- [ ] Specific, measurable expected results (not "should work")
- [ ] Test independence verified (no dependencies on other tests)

### Exercise 2: Organize by Module (60 min)
- [ ] Module breakdown created with test counts
- [ ] Priority matrix calculated (S0-S4 distribution)
- [ ] Test suites defined:
  - [ ] Smoke Suite: 10-15 critical tests
  - [ ] Regression Suite: 30-40 S0-S2 tests
  - [ ] Full Suite: All 50+ tests
- [ ] Execution order recommendations documented
- [ ] Execution time estimates provided per suite

### Exercise 3: Traceability Matrix (60 min)
- [ ] 13+ functional requirements extracted/defined
- [ ] RTM table created with all requirements
- [ ] Every requirement mapped to at least 1 test case
- [ ] All 50+ test cases mapped to requirements
- [ ] Requirements coverage calculated (target: 100%)
- [ ] Module coverage calculated (Authentication, Products, Cart, Checkout)
- [ ] Forward traceability documented (Requirements → Tests)
- [ ] Backward traceability documented (Tests → Requirements)
- [ ] Gap analysis completed (no orphaned tests/requirements)
- [ ] Used template from `curriculum/templates/traceability-matrix-template.md`

### Exercise 4: Test Data Management (45 min)
- [ ] Valid test data documented:
  - [ ] All SauceDemo users (standard_user, problem_user, etc.)
  - [ ] All 6 products
  - [ ] Valid checkout data
- [ ] Invalid test data documented:
  - [ ] Invalid login credentials
  - [ ] Invalid checkout data
- [ ] Boundary test data documented:
  - [ ] Cart quantity boundaries (0, 1, 6 items)
  - [ ] Field length boundaries
- [ ] Security test data documented:
  - [ ] SQL injection payloads
  - [ ] XSS payloads
- [ ] Test data file organization proposed

### Exercise 5: Test Case Review (45 min)
- [ ] 10 test cases selected for review (diverse sample)
- [ ] Review checklist applied to all 10:
  - [ ] Completeness checked
  - [ ] Clarity checked
  - [ ] Correctness checked
  - [ ] Testability checked
  - [ ] Coverage checked
- [ ] Issues documented with severity
- [ ] Summary report created
- [ ] Common patterns identified (good and bad)
- [ ] Action items listed
- [ ] Personal learnings documented

### Exercise 6: GitHub Projects Test Management (60 min)
- [ ] 10-15+ test cases created as GitHub issues
- [ ] GitHub Issue Template used (`.github/ISSUE_TEMPLATE/02-test-case.yml`)
- [ ] Labels added to all issues:
  - [ ] Test type labels (test:ui, test:smoke, etc.)
  - [ ] Severity labels (severity:s0-blocker through s4-trivial)
- [ ] All issues added to "SauceDemo Test Suite" GitHub Project
- [ ] Custom fields set for all issues:
  - [ ] Test Type
  - [ ] Test Suite
  - [ ] Severity
  - [ ] Module
  - [ ] Automation Status (Not Automated)
  - [ ] Last Run Status (Not Run)
- [ ] GitHub Project views explored (Test Inventory, Regression Suite, Automation Backlog)
- [ ] Screenshots captured
- [ ] Reflection on benefits written

---

## 📂 Deliverables

### Week 8 Deliverables (6 files)
- [ ] `mentee-work/week-08/write-50+-test-cases.md` - 50+ test cases
- [ ] `mentee-work/week-08/organize-by-module.md` - Organization structure
- [ ] `mentee-work/week-08/traceability-matrix.md` - RTM with 100% coverage
- [ ] `mentee-work/week-08/test-data-management.md` - Test data strategy
- [ ] `mentee-work/week-08/test-case-review.md` - Review findings
- [ ] `mentee-work/week-08/test-management-organization.md` - GitHub Projects setup
- [ ] All work committed to GitHub with clear commit messages
- [ ] Pull Request created with Week 8 submission template

---

## ⏱️ Time Tracking

| Activity | Estimated | Actual |
|----------|-----------|--------|
| Tutorial Reading | 2-3 hrs | ___ |
| Exercise 1 (50+ Test Cases) | 3 hrs | ___ |
| Exercise 2 (Organization) | 1 hr | ___ |
| Exercise 3 (RTM) | 1 hr | ___ |
| Exercise 4 (Test Data) | 45 min | ___ |
| Exercise 5 (Review) | 45 min | ___ |
| Exercise 6 (GitHub Projects) | 1 hr | ___ |
| Documentation & Commit | 30 min | ___ |
| **Total** | **9-10 hrs** | **___** |

---

## 🎯 Key Learning Outcomes

By the end of Week 8, you should be able to:
- [ ] Write clear, comprehensive, independent test cases
- [ ] Apply test design techniques (EP, BVA, Decision Tables, State Transitions)
- [ ] Organize test cases by module, priority, and test suite
- [ ] Create and maintain Requirements Traceability Matrix
- [ ] Manage test data (valid, invalid, boundary, security)
- [ ] Review test cases for quality using systematic checklist
- [ ] Use GitHub Projects for test management
- [ ] Explain why test independence matters
- [ ] Articulate the difference between test types (UI, E2E, Smoke, Regression)
- [ ] Understand S0-S4 severity model

---

## ✅ Quality Gates (Must Pass Before Submission)

### Minimum Requirements
- [ ] ✅ At least 50 test cases created (60+ recommended)
- [ ] ✅ All modules covered (Login: 15+, Products: 10+, Cart: 15+, Checkout: 20+)
- [ ] ✅ Traceability Matrix shows 100% requirements coverage
- [ ] ✅ No orphaned tests (all tests map to requirements)
- [ ] ✅ No untested requirements (all requirements have tests)
- [ ] ✅ Test cases use TC-[MODULE]-[###] format
- [ ] ✅ All test cases have specific, measurable expected results
- [ ] ✅ All test cases are independent (no dependencies)
- [ ] ✅ At least 10-15 test cases in GitHub Projects
- [ ] ✅ All 6 exercise deliverables submitted

### FAANG-Level Excellence
- [ ] 🌟 Test cases include security tests (SQL injection, XSS)
- [ ] 🌟 Boundary tests cover edge cases (0 items, max items, field lengths)
- [ ] 🌟 RTM includes forward AND backward traceability
- [ ] 🌟 Test review identifies specific improvements with examples
- [ ] 🌟 GitHub Projects custom fields fully configured
- [ ] 🌟 Test data management includes file organization strategy
- [ ] 🌟 End-to-end smoke test included (TC-CHECKOUT-020)

---

## 📊 Self-Assessment

Before submitting Week 8, rate yourself:

| Dimension | Rating (1-5) | Notes |
|-----------|--------------|-------|
| **Completeness** | ___ / 5 | All 6 exercises completed, 50+ tests written |
| **Quality** | ___ / 5 | Test cases professional, specific, clear |
| **Organization** | ___ / 5 | Logical structure, clear prioritization |
| **Traceability** | ___ / 5 | RTM complete, 100% coverage, gap analysis |
| **Critical Thinking** | ___ / 5 | Test design techniques applied, security included |
| **Professionalism** | ___ / 5 | Clean formatting, GitHub integration |
| **Overall** | ___ / 5 | |

**Reflection:**
- What was most challenging this week?
- What are you most proud of?
- What will you do differently next week?

---

## 🔗 Related Resources

### Templates Used
- `curriculum/templates/test-case-template.md`
- `curriculum/templates/traceability-matrix-template.md`

### GitHub
- `.github/ISSUE_TEMPLATE/02-test-case.yml` (Test Case template)
- GitHub Projects: "SauceDemo Test Suite"

### Tutorial Sections to Review if Stuck
- Section 1: Anatomy of a Good Test Case (lines 27-262)
- Section 4: Requirements Traceability Matrix (lines 442-530)
- Section 6: Test Case Review Checklist (lines 723-875)

---

## ✅ Week Completion

**Status:**
- [ ] Not Started
- [ ] In Progress (after reading tutorial)
- [ ] Exercises In Progress (after completing Exercise 1)
- [ ] Ready for Review (all 6 exercises complete)
- [ ] Completed (PR approved and merged)

**Completion Date:** _____________

**Mentor Sign-Off:** _____________

---

**Remember:** Week 8 deliverables are portfolio-ready. You'll show these test cases and traceability matrix in interviews! 🎯
