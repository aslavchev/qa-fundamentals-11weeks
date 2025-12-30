# Week 11: Python for Test Data & APIs - Checklist

## 📋 Weekly Goals
- [ ] Install Python 3.11+ development environment successfully
- [ ] Generate test data using Faker library (50+ records)
- [ ] Save test data to CSV and JSON files programmatically
- [ ] Perform basic API testing using requests library
- [ ] Understand when to use Python vs manual testing
- [ ] Create reusable Python scripts for QA tasks

---

## 📚 Tutorial Completion
- [ ] Read complete tutorial.md (2-3 hours)
- [ ] Study Section 1: Why Python for QA?
- [ ] Study Section 2: Python Installation & Setup
- [ ] Study Section 3: Python Basics (variables, data types, functions)
- [ ] Study Section 4: Test Data Generation with Faker
- [ ] Study Section 5: File Handling (CSV & JSON)
- [ ] Study Section 6: API Testing with requests library
- [ ] Study Section 7: Python for SauceDemo testing
- [ ] Run all tutorial code examples in your environment
- [ ] Answer self-assessment questions at end of tutorial

---

## 🧪 Exercises Completion

### Exercise 1: Python Setup & First Script (30 min)
- [ ] Python installation completed
  - [ ] Python 3.11+ installed
  - [ ] `python --version` command works
  - [ ] Python added to PATH (Windows)
  - [ ] pip package manager verified (`pip --version`)
- [ ] VS Code + Python extension installed
  - [ ] VS Code downloaded and installed
  - [ ] Python extension by Microsoft installed
  - [ ] Syntax highlighting works for `.py` files
- [ ] First script created: `hello_qa.py`
  - [ ] Script prints system info (Python version, OS)
  - [ ] Script runs without errors
  - [ ] Output captured in `python-setup.md`
- [ ] Environment verified
  - [ ] Python works in terminal/command prompt
  - [ ] Can run scripts from VS Code
  - [ ] Can run scripts from command line

### Exercise 2: Test Data Generator (60 min)
- [ ] Faker library installed (`pip install faker`)
- [ ] Import Faker successfully in Python script
- [ ] Script 1: Single record generator completed
  - [ ] Generates 1 random first name, last name, zip code
  - [ ] Prints to console successfully
  - [ ] Code saved in `mentee-work/week-11/` folder
- [ ] Script 2: Multiple records generator completed
  - [ ] Generates 50 random test records
  - [ ] Uses loop to iterate 50 times
  - [ ] Prints all records to console
- [ ] Script 3: Edge cases added
  - [ ] Empty string test case added
  - [ ] Very long name test case added (50+ characters)
  - [ ] Special character test case added
  - [ ] Numeric zip code test case added
  - [ ] Total dataset = 50 random + 10 edge cases = 60 records
- [ ] Output documented in `test-data-generator.md`
  - [ ] Script code included in markdown
  - [ ] Sample output (first 10 records) shown
  - [ ] Total record count verified (60 records)
- [ ] Reflection answered: "How much time did this save vs Excel?"

### Exercise 3: CSV/JSON File Handling (60 min)
- [ ] CSV module imported successfully
- [ ] JSON module imported successfully
- [ ] Script 4: Save to CSV completed
  - [ ] Opens CSV file in write mode
  - [ ] Writes header row (test_id, first_name, last_name, zip_code, expected_result)
  - [ ] Writes 60 data rows
  - [ ] File saved as `checkout_test_data.csv`
  - [ ] CSV file opens in Excel/Numbers/Sheets
- [ ] Script 5: Save to JSON completed
  - [ ] Converts data to JSON format
  - [ ] Writes to `checkout_test_data.json`
  - [ ] JSON is properly formatted (indented)
  - [ ] JSON file is valid (can be parsed)
- [ ] Script 6: Read from CSV completed
  - [ ] Reads `checkout_test_data.csv`
  - [ ] Prints total count of test cases
  - [ ] Prints first 5 records to verify data
- [ ] Script 7: Read from JSON completed
  - [ ] Reads `checkout_test_data.json`
  - [ ] Parses JSON successfully
  - [ ] Prints total count of test cases
  - [ ] Prints first 5 records to verify data
- [ ] Both file formats created and verified
  - [ ] CSV file exists and has 61 rows (1 header + 60 data)
  - [ ] JSON file exists and has 60 objects
  - [ ] Both files contain same data
- [ ] Documentation completed in `csv-json-handling.md`
  - [ ] All 4 scripts included (save CSV, save JSON, read CSV, read JSON)
  - [ ] Screenshots of CSV file in Excel
  - [ ] Screenshots of JSON file in text editor
  - [ ] File sizes noted

### Exercise 4: Simple API Testing (60 min)
- [ ] requests library installed (`pip install requests`)
- [ ] JSONPlaceholder API explored (https://jsonplaceholder.typicode.com)
- [ ] Test 1: GET request completed
  - [ ] GET /posts/1 endpoint tested
  - [ ] Status code verified (200 OK)
  - [ ] Response body parsed as JSON
  - [ ] Fields validated (userId, id, title, body)
  - [ ] Assertions added to verify data
- [ ] Test 2: POST request completed
  - [ ] POST /posts endpoint tested
  - [ ] Request body created (title, body, userId)
  - [ ] Status code verified (201 Created)
  - [ ] Response includes new post ID
  - [ ] Assertion added to verify post created
- [ ] Test 3: PUT request completed
  - [ ] PUT /posts/1 endpoint tested
  - [ ] Request body with updated title/body
  - [ ] Status code verified (200 OK)
  - [ ] Response includes updated data
- [ ] Test 4: DELETE request completed
  - [ ] DELETE /posts/1 endpoint tested
  - [ ] Status code verified (200 OK)
  - [ ] Response verified (empty object {})
- [ ] Error scenario tested
  - [ ] GET /posts/99999 (non-existent post)
  - [ ] Status code verified (404 Not Found)
  - [ ] Error handling added (try/except)
- [ ] All 5 test scripts created
  - [ ] `api_get_test.py`
  - [ ] `api_post_test.py`
  - [ ] `api_put_test.py`
  - [ ] `api_delete_test.py`
  - [ ] `api_error_test.py`
- [ ] Documentation completed in `api-testing.md`
  - [ ] All 5 scripts included
  - [ ] Output screenshots for each test
  - [ ] HTTP methods explained (GET, POST, PUT, DELETE)
  - [ ] Status codes documented (200, 201, 404)

### Exercise 5: Complete Test Data Script (45 min)
- [ ] Final script combines all learnings
- [ ] Script structure completed
  - [ ] Imports (Faker, csv, json, datetime)
  - [ ] `generate_random_data(count=50)` function
  - [ ] `generate_edge_cases()` function
  - [ ] `save_to_csv(data, filename)` function
  - [ ] `save_to_json(data, filename)` function
  - [ ] `main()` function to orchestrate everything
- [ ] Random data generation (50 records)
  - [ ] First name, last name, zip code
  - [ ] Test ID auto-generated (TEST-001, TEST-002, etc.)
  - [ ] Expected result field added ("Pass" for valid data)
- [ ] Edge case generation (10 records)
  - [ ] Empty strings
  - [ ] Very long names (50+ chars)
  - [ ] Special characters
  - [ ] Numeric values
  - [ ] SQL injection attempts
  - [ ] Expected result field = "Fail" or "Error"
- [ ] Metadata added
  - [ ] Total test cases count
  - [ ] Generated timestamp
  - [ ] Generator version
  - [ ] Purpose/description
- [ ] Output files generated
  - [ ] `saucedemo_checkout_tests.csv` (61 rows: header + 60 data)
  - [ ] `saucedemo_checkout_tests.json` (60 objects with metadata)
  - [ ] Both files saved in `mentee-work/week-11/`
- [ ] Script documentation completed
  - [ ] Code saved as `test_data_master.py`
  - [ ] Documentation in `complete-script.md`
  - [ ] Code includes comments explaining each section
  - [ ] Sample output shown (first 10 records)
  - [ ] Instructions to run script included
- [ ] Portfolio quality achieved
  - [ ] Professional variable names (no `x`, `y`, `z`)
  - [ ] Functions have docstrings
  - [ ] Error handling included (try/except for file operations)
  - [ ] Code is readable and well-structured
- [ ] Reflection completed
  - [ ] Time saved calculation (manual vs Python)
  - [ ] When to use Python vs manual testing
  - [ ] How this applies to your QA workflow

---

## 📂 Deliverables

### Week 11 Deliverables (5 markdown files + 10+ Python scripts)
- [ ] `mentee-work/week-11/python-setup.md` - Environment verification
- [ ] `mentee-work/week-11/test-data-generator.md` - Faker scripts (3 scripts)
- [ ] `mentee-work/week-11/csv-json-handling.md` - File handling scripts (4 scripts)
- [ ] `mentee-work/week-11/api-testing.md` - API test scripts (5 scripts)
- [ ] `mentee-work/week-11/complete-script.md` - Final master script
- [ ] `mentee-work/week-11/hello_qa.py` - First Python script
- [ ] `mentee-work/week-11/test_data_master.py` - Final complete script
- [ ] `mentee-work/week-11/saucedemo_checkout_tests.csv` - Generated CSV file
- [ ] `mentee-work/week-11/saucedemo_checkout_tests.json` - Generated JSON file
- [ ] All Python scripts run without errors
- [ ] All work committed to GitHub with clear commit messages
- [ ] Pull Request created with Week 11 submission template

---

## ⏱️ Time Tracking

| Activity | Estimated | Actual |
|----------|-----------|--------|
| Tutorial Reading | 2-3 hrs | ___ |
| Exercise 1 (Python Setup) | 30 min | ___ |
| Exercise 2 (Test Data) | 60 min | ___ |
| Exercise 3 (CSV/JSON) | 60 min | ___ |
| Exercise 4 (API Testing) | 60 min | ___ |
| Exercise 5 (Complete Script) | 45 min | ___ |
| Documentation & Commit | 30 min | ___ |
| **Total** | **7-8 hrs** | **___** |

---

## 🎯 Key Learning Outcomes

By the end of Week 11, you should be able to:
- [ ] Install and configure Python development environment
- [ ] Explain when Python is more efficient than manual testing
- [ ] Use Faker library to generate realistic test data
- [ ] Save test data to CSV and JSON file formats
- [ ] Read data from CSV and JSON files programmatically
- [ ] Perform GET, POST, PUT, DELETE API requests using requests library
- [ ] Validate API responses (status codes, response body)
- [ ] Handle errors in Python scripts (try/except)
- [ ] Write reusable functions for QA tasks
- [ ] Calculate time saved by automation vs manual work
- [ ] Understand Python basics: variables, loops, functions, imports
- [ ] Use Python for data-driven testing (load test data from files)

---

## ✅ Quality Gates (Must Pass Before Submission)

### Minimum Requirements
- [ ] ✅ **Python 3.11+ installed and verified** (Exercise 1)
  - [ ] `python --version` shows 3.11 or higher
  - [ ] pip works (`pip --version`)
  - [ ] VS Code + Python extension installed
- [ ] ✅ **Test data generator creates 60 records** (Exercise 2)
  - [ ] 50 random records using Faker
  - [ ] 10 edge case records
  - [ ] Output documented in markdown
- [ ] ✅ **CSV and JSON files created successfully** (Exercise 3)
  - [ ] Both file formats exist
  - [ ] Both contain same 60 test records
  - [ ] Files can be opened and read
- [ ] ✅ **5 API tests completed** (Exercise 4)
  - [ ] GET, POST, PUT, DELETE, Error scenario
  - [ ] All tests run without errors
  - [ ] Status codes validated
- [ ] ✅ **Complete script generates final dataset** (Exercise 5)
  - [ ] `test_data_master.py` runs successfully
  - [ ] Outputs CSV and JSON files
  - [ ] 60 total records (50 random + 10 edge cases)
  - [ ] Metadata included (timestamp, count)
- [ ] ✅ **All Python scripts run without syntax errors**
  - [ ] No `SyntaxError`, `NameError`, `ImportError`
  - [ ] Scripts can be executed from command line
  - [ ] Scripts documented in markdown files

### FAANG-Level Excellence
- [ ] 🌟 **Code is clean and professional**
  - [ ] Variable names are descriptive (not `x`, `y`, `data`)
  - [ ] Functions have docstrings explaining purpose
  - [ ] Comments explain "why", not just "what"
  - [ ] Consistent indentation (4 spaces, not tabs)
- [ ] 🌟 **Error handling included**
  - [ ] try/except blocks for file operations
  - [ ] try/except blocks for API requests
  - [ ] Meaningful error messages printed
- [ ] 🌟 **Test data includes realistic edge cases**
  - [ ] Not just random data, but thoughtful edge cases
  - [ ] SQL injection attempts (e.g., `' OR '1'='1`)
  - [ ] Unicode characters (e.g., emoji in names)
  - [ ] Boundary values (very long strings, empty strings)
- [ ] 🌟 **API tests include assertions**
  - [ ] Not just printing response, but validating
  - [ ] Uses `assert` statements (e.g., `assert status_code == 200`)
  - [ ] Validates response structure (e.g., `assert 'title' in response`)
- [ ] 🌟 **Documentation is detailed and includes screenshots**
  - [ ] Code blocks are properly formatted (```python)
  - [ ] Screenshots show actual output in terminal
  - [ ] Instructions are clear enough for another person to follow
- [ ] 🌟 **Reflection shows deep understanding**
  - [ ] Time savings calculated (e.g., "Manual: 2 hours, Python: 5 seconds")
  - [ ] Explains when to use Python vs when manual is better
  - [ ] Connects Python to real QA workflow (not just theory)
- [ ] 🌟 **Portfolio-ready final script**
  - [ ] Could show `test_data_master.py` in an interview
  - [ ] Code demonstrates professional Python practices
  - [ ] Solves a real QA problem (generating test data at scale)

---

## 📊 Self-Assessment

Before submitting Week 11, rate yourself:

| Dimension | Rating (1-5) | Notes |
|-----------|--------------|-------|
| **Completeness** | ___ / 5 | All 5 exercises completed, 60 test records generated |
| **Quality** | ___ / 5 | Scripts run without errors, code is clean and documented |
| **Accuracy** | ___ / 5 | API tests validate correctly, file formats correct |
| **Critical Thinking** | ___ / 5 | Edge cases thoughtful, time savings calculated |
| **Professionalism** | ___ / 5 | Code is readable, comments helpful, error handling included |
| **Portfolio Readiness** | ___ / 5 | Could show Python scripts in interview |
| **Overall** | ___ / 5 | |

**Reflection:**
- What was most challenging this week?
- What are you most proud of?
- How much time did Python save vs manual test data creation?
- When would you NOT use Python for QA tasks?
- How does this connect to your Week 8-10 work?

---

## 🔗 Related Resources

### Templates Used
- Python script templates (in exercises.md for each exercise)
- CSV file format (header row + data rows)
- JSON file format (array of objects with metadata)

### Week 8-10 Connection
- Week 8: You wrote 60 test cases manually
- Week 9: You converted test cases to BDD format
- Week 10: You found bugs in SauceDemo manually
- **Week 11**: Now automate test data creation with Python!

**Example:** Your Week 8 checkout test cases needed test data (first name, last name, zip). Week 11 shows you how to generate that data in 5 seconds instead of typing it manually for 2 hours.

### Tutorial Sections to Review if Stuck
- Section 2: Python Installation (if setup fails)
- Section 4: Faker library usage (if test data generation confusing)
- Section 5: File handling (if CSV/JSON operations fail)
- Section 6: requests library (if API testing unclear)

---

## ✅ Week Completion

**Status:**
- [ ] Not Started
- [ ] In Progress (after reading tutorial)
- [ ] Exercises In Progress (after completing Exercise 1)
- [ ] Ready for Review (all 5 exercises complete)
- [ ] Completed (PR approved and merged)

**Completion Date:** _____________

**Mentor Sign-Off:** _____________

---

## 💡 Tips for Success

**Exercise 1 (Python Setup):**
- Windows users: MUST check "Add Python to PATH" during installation
- macOS/Linux users: Use `python3` instead of `python` command
- If `pip` doesn't work, try `pip3` or `python -m pip`
- VS Code extension matters - get "Python" by Microsoft (not third-party)

**Exercise 2 (Test Data):**
- Faker is random - your output won't match tutorial exactly (that's OK!)
- Start with 5 records first, then scale to 50 (easier to debug)
- Edge cases are more valuable than random data - think like a QA!
- Don't copy/paste code blindly - type it yourself to learn

**Exercise 3 (CSV/JSON):**
- CSV = Excel-friendly, JSON = API-friendly
- Always close files after writing (`with open()` does this automatically)
- Check file exists before trying to read it
- CSV header row must match data columns exactly
- JSON must be valid - use https://jsonlint.com/ to validate

**Exercise 4 (API Testing):**
- JSONPlaceholder is a fake API - POST/PUT/DELETE don't actually save data
- Status codes matter: 200 (OK), 201 (Created), 404 (Not Found)
- Always check status code before parsing response JSON
- Use try/except for API requests (network can fail)
- Print response to debug - helps understand API behavior

**Exercise 5 (Complete Script):**
- Break big script into small functions (easier to debug)
- Test each function separately before combining
- Add metadata (timestamp, count) - makes output professional
- Use `if __name__ == "__main__":` to make script runnable
- Version your script (v1.0, v1.1) as you improve it

**Common Mistakes:**
1. **Forgetting to install libraries:** Run `pip install faker requests` BEFORE running scripts
2. **Not activating venv (if using one):** Commands won't work if venv not active
3. **File path issues:** Use absolute paths if relative paths fail
4. **Not checking errors:** Use `try/except` to handle failures gracefully
5. **Copying code without understanding:** Type it yourself, run it line by line

**Time Management:**
- Don't spend 3 hours debugging Python installation - ask for help after 30 min
- Run code frequently (every 5 lines) to catch errors early
- Save your scripts often (Ctrl+S / Cmd+S)
- Commit working code to GitHub (even if incomplete) - better than losing work

**Portfolio Thinking:**
- "Show me a Python script you wrote for testing" → Exercise 5 `test_data_master.py`
- "How do you handle test data at scale?" → "I use Faker + Python to generate 1000s of records"
- "Give an example of automation you've done" → "I automated test data creation, saving 2 hours per test cycle"

---

**Remember:** Week 11 is your first Python week! Don't try to become a Python expert - focus on solving real QA problems. By the end, you'll be able to generate test data in seconds instead of hours. That's the power of automation! 🚀
