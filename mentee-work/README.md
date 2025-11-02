# Mentee Work Directory

This directory contains all your completed weekly exercises and deliverables.

## 📁 Directory Structure

```
mentee-work/
├── README.md (this file)
├── week-01/  (Week 1: QA Foundations & SDLC exercises)
├── week-02/  (Week 2: Test Levels exercises)
├── week-03/  (Week 3: Functional Testing Types exercises)
├── week-04/  (Week 4: Non-Functional Testing exercises)
├── week-05/  (Week 5: Test Design Techniques Basic exercises)
├── week-06/  (Week 6: Test Design Techniques Advanced exercises)
├── week-07/  (Week 7: Test Planning & Strategy exercises)
├── week-08/  (Week 8: Test Case Design & Management exercises)
├── week-09/  (Week 9: Agile Testing & Methodologies exercises)
├── week-10/  (Week 10: Defect Management exercises)
└── week-11/  (Week 11: Python for Test Data & APIs exercises)
```

## 🔄 Proper Git Workflow (REQUIRED)

### For Each Week:

**Step 1: Create Feature Branch**
```bash
git checkout main
git pull origin main
git checkout -b week-XX-work
```

**Step 2: Complete Exercises**
- Work in `mentee-work/week-XX/` folder
- Follow deliverable names from `week-XX-.../exercises.md`
- Commit frequently as you complete each exercise

**Step 3: Commit Your Work**
```bash
git add mentee-work/week-XX/
git commit -m "Week XX exercises complete

- Exercise 1: [name]
- Exercise 2: [name]
- Exercise 3: [name]
- Exercise 4: [name]
- Exercise 5: [name]"
```

**Step 4: Push Branch**
```bash
git push -u origin week-XX-work
```

**Step 5: Create Pull Request**
1. Go to GitHub repository
2. Click "Pull Requests" tab
3. Click "New Pull Request"
4. Select your branch: `week-XX-work`
5. Add title: `Week XX: [Topic] - Exercises Complete`
6. Add description summarizing what you completed
7. Click "Create Pull Request"

**Step 6: Wait for Review**
- Your mentor will review your PR
- Address any feedback/corrections
- Once approved, mentor will merge

### Important Notes:

- ✅ **Always use feature branches** - Never commit directly to `main`
- ✅ **One branch per week** - Keep work organized
- ✅ **Wait for approval** - Don't merge your own PRs
- ✅ **Use English** - All content must be in English
- ✅ **Follow naming conventions** - Use hyphens in file names (e.g., `qa-qc-testing-comparison.md`)

## 📝 File Naming Convention

**Use hyphens, not underscores:**

✅ **Correct:**
- `qa-qc-testing-comparison.md`
- `sdlc-comparison.md`
- `saucedemo-analysis.md`

❌ **Incorrect:**
- `qa_qc_testing_comparison.md`
- `sdlc_comparison.md`
- `saucedemo_analysis.md`

## 📂 Example Week Structure

```
mentee-work/week-01/
├── qa-qc-testing-comparison.md
├── sdlc-comparison.md
├── saucedemo-analysis.md
├── sdlc-activities.md
└── quality-attributes.md
```

## 🎯 Deliverables Checklist

Each week's exercises specify the exact deliverable file names. Make sure to:
- [ ] Use the exact file names specified in `exercises.md`
- [ ] Save files in the correct `mentee-work/week-XX/` directory
- [ ] Complete all required parts (Part A, Part B, Part C, etc.)
- [ ] Write all content in English
- [ ] Commit with clear commit messages

## 🚀 Quick Reference Commands

**Start new week:**
```bash
git checkout main && git pull && git checkout -b week-XX-work
```

**Commit progress:**
```bash
git add mentee-work/week-XX/
git commit -m "Completed Exercise X"
```

**Push for review:**
```bash
git push -u origin week-XX-work
# Then create PR on GitHub
```

**After PR merged, start next week:**
```bash
git checkout main
git pull origin main
git checkout -b week-XX-work
```

---

**Questions?** Ask your mentor or create a GitHub Issue with tag `question`.

**Good luck with your QA journey!** 🎓
