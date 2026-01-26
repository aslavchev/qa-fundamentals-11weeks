# Week 10 - Exercise 4: Defect Metrics Dashboard

**Name:** Kamen Asenov  
**Date:** 2026-01-18  
**Reporting Period:** Week 10 Testing Cycle

---

## Executive Summary

**Total Defects Found:** 10  
**Test Cases Executed:** 60 (from Week 8)  
**Defect Density:** 0.17 defects per test case  
**Defect Removal Efficiency (DRE):** 83.3%  
**Defect Leakage:** 16.7%

**Quality Assessment:** ⚠️ Concern  
**Key Finding:** Most defects are medium-severity UX/state issues, with Checkout identified as the highest-risk area.

---

## Metric 1: Defect Density

**Formula:** Total Defects / Test Cases Executed  
**Calculation:** 10 defects / 60 test cases = **0.17** defects per test case

**Interpretation:**
- Industry Benchmark (first cycle): **0.10 – 0.25**
- Our Result: **Within benchmark**
- **Analysis:**  
  Density indicates a normal level of issues for an initial testing cycle. Exploratory testing still uncovered meaningful state and UX risks.

---

## Metric 2: Defect Distribution by Severity

| Severity | Count | Percentage | Target Range | Status |
|----------|-------|------------|--------------|--------|
| S1 (Critical) | 0 | 0% | < 10% | ✅ |
| S2 (High) | 1 | 10% | 20–30% | ⚠️ |
| S3 (Medium) | 6 | 60% | 40–50% | ⚠️ |
| S4 (Low) | 3 | 30% | 20–30% | ✅ |
| **Total** | **10** | **100%** | - | - |

**Text Chart:**
- S2 High: ████ 10%  
- S3 Medium: ████████████████████ 60%  
- S4 Low: ██████████ 30%

**Analysis:**
- No critical defects found (good baseline stability)
- Higher share of S3 suggests UX/state/validation issues that can impact confidence
- Low severity issues are still present but within expected range

---

## Metric 3: Defect Distribution by Module

| Module | Count | Percentage | Status |
|--------|-------|------------|--------|
| Login | 2 | 20% | Normal |
| Products | 2 | 20% | Normal |
| Cart | 2 | 20% | Normal |
| Checkout | 3 | 30% | ⚠️ Hotspot |
| Cross-cutting | 1 | 10% | Normal |
| **Total** | **10** | **100%** | - |

**Text Chart:**
- Login: ██████ (2)  
- Products: ██████ (2)  
- Cart: ██████ (2)  
- Checkout: █████████ (3) ⚠️  
- Cross-cutting: ███ (1)

**Defect Hotspot:** Checkout (3 bugs, 30%)

**Analysis:**
Checkout defects include state validation and navigation risks. In real e-commerce, checkout integrity is a high-risk area and should receive extra regression + negative-flow coverage.

---

## Metric 4: Defect Removal Efficiency (DRE)

**Simulated Scenario:**
- Bugs found during testing: 10
- Bugs assumed to escape to production: 2  
  - BUG-003 (Remove without confirmation – UX)
  - BUG-008 (Persistent login error message – UX)

**Total Defects:** 12

**Formula:** (Testing Defects / Total Defects) × 100%  
**Calculation:** 10 / 12 × 100% = **83.3%**

**Target:** 90%+  
**Result:** ❌ Below target

**Analysis:**
Intermittent and low-severity UX issues are more likely to leak. Increasing focused UX exploratory sessions and adding explicit UX acceptance expectations could improve DRE.

---

## Metric 5: Defect Leakage

**Formula:** (Production Defects / Total Defects) × 100%  
**Calculation:** 2 / 12 × 100% = **16.7%**

**Target:** < 10%  
**Result:** ❌ Exceeds target

**Escaped Bugs (Simulated):**
1. **BUG-003:** No confirmation/undo on removal – low impact, easy to miss
2. **BUG-008:** Error message persists while editing – minor UX issue

**Analysis:**
Leakage is mainly driven by UX/visibility issues, which suggests improving UX checks and including them in Definition of Done / acceptance criteria where relevant.

---

## Metric 6: Defect Age (Not Applicable)

**Note:**  
Not tracked in this exercise. In real projects, defect age helps identify workflow bottlenecks and SLA performance.

---

## Key Insights

### 1. Overall Quality
SauceDemo has acceptable functional quality, but several medium issues exist in state handling and UX.

### 2. Testing Effectiveness
Exploratory testing was effective for discovering state and workflow risks, but minor UX issues are more likely to escape.

### 3. Risk Areas
Checkout is the riskiest module and should receive more negative-flow and state validation testing.

### 4. Recommendations
- Add explicit negative/state tests for checkout (direct URL, back/refresh behavior)
- Add UX exploratory session checklist for “error message handling” and “mobile/responsive UI”
- Update DoD: “State transitions validated (Back/Refresh/Direct URL)”
- Add input-format validation expectations for postal code

---

## Metrics Dashboard Summary

| Metric | Value | Target | Status |
|--------|-------|--------|--------|
| Defect Density | 0.17 | 0.10–0.25 | ✅ |
| DRE | 83.3% | > 90% | ❌ |
| Defect Leakage | 16.7% | < 10% | ❌ |
| S1 Critical % | 0% | < 10% | ✅ |
| Defect Hotspot | Checkout | Even distribution | ⚠️ |

**Overall Grade:** **B**  
**Justification:** Solid functional baseline, but improvements needed in UX coverage and state-related regression around checkout.
