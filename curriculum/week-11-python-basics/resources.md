# Week 11: Python for Test Data & APIs - Resources

This document curates the best learning resources for **Python for QA tasks** - focused specifically on test data generation and API testing, not comprehensive Python programming.

---

## 🎥 Essential Videos

### Python Installation & Setup

1. **Python Installation Tutorial (Windows)** ⭐ START HERE (Windows users)
   - URL: https://www.youtube.com/results?search_query=python+installation+windows+2024
   - Duration: 10-15 minutes
   - Why watch: Step-by-step installation, troubleshooting "Add to PATH" issues
   - Key topics: Download, install, verify, pip setup
   - **Note:** MUST check "Add Python to PATH" during installation!

2. **Python Installation Tutorial (macOS)** ⭐ START HERE (Mac users)
   - URL: https://www.youtube.com/results?search_query=python+installation+mac+homebrew
   - Duration: 10 minutes
   - Why watch: Homebrew installation method (recommended for Mac)
   - Key topics: `brew install python3`, verify installation

3. **VS Code + Python Setup**
   - URL: https://www.youtube.com/results?search_query=vs+code+python+setup+2024
   - Duration: 15 minutes
   - Why watch: Configure VS Code for Python development
   - Key topics: Python extension, running scripts, debugging

### Python Basics (for QA)

4. **Python in 100 Seconds** (Fireship)
   - URL: https://www.youtube.com/watch?v=x7X9w_GIm1s
   - Duration: 2 minutes
   - Why watch: Quick overview of Python syntax
   - Key topics: Variables, functions, imports

5. **Python for Beginners - Variables and Data Types**
   - URL: https://www.youtube.com/results?search_query=python+variables+data+types+beginners
   - Duration: 15-20 minutes
   - Why watch: Understand strings, integers, lists, dictionaries
   - Key topics: `name = "John"`, `age = 25`, `data = ["a", "b", "c"]`

6. **Python Functions Explained**
   - URL: https://www.youtube.com/results?search_query=python+functions+explained+beginners
   - Duration: 15 minutes
   - Why watch: Learn to write reusable code
   - Key topics: `def`, parameters, return values, docstrings

### Test Data Generation

7. **Faker Library Tutorial** ⭐ CRITICAL FOR WEEK 11
   - URL: https://www.youtube.com/results?search_query=python+faker+library+tutorial
   - Duration: 20-25 minutes
   - Why watch: Generate realistic test data (names, emails, addresses)
   - Key topics: `fake.name()`, `fake.email()`, `fake.address()`

8. **Test Data Generation for QA**
   - URL: https://www.youtube.com/results?search_query=test+data+generation+python+qa
   - Duration: 15 minutes
   - Why watch: Real QA use case - generating thousands of test records
   - Key topics: Edge cases, boundary values, realistic vs random data

### CSV and JSON File Handling

9. **Python CSV Module Tutorial**
   - URL: https://www.youtube.com/results?search_query=python+csv+module+tutorial
   - Duration: 15-20 minutes
   - Why watch: Read/write CSV files for test data
   - Key topics: `csv.writer()`, `csv.DictWriter()`, headers, rows

10. **Python JSON Module Tutorial**
    - URL: https://www.youtube.com/results?search_query=python+json+module+tutorial
    - Duration: 15 minutes
    - Why watch: Handle JSON files for API testing
    - Key topics: `json.dumps()`, `json.loads()`, pretty printing

### API Testing with Python

11. **Python requests Library Tutorial** ⭐ CRITICAL FOR WEEK 11
    - URL: https://www.youtube.com/results?search_query=python+requests+library+tutorial
    - Duration: 25-30 minutes
    - Why watch: Perform API testing without Postman
    - Key topics: GET, POST, PUT, DELETE, headers, status codes

12. **API Testing with Python (Complete Guide)**
    - URL: https://www.youtube.com/results?search_query=api+testing+python+requests
    - Duration: 30-40 minutes
    - Why watch: End-to-end API testing workflow
    - Key topics: Authentication, assertions, response validation

13. **JSONPlaceholder API Testing Tutorial**
    - URL: https://www.youtube.com/results?search_query=jsonplaceholder+api+python+tutorial
    - Duration: 20 minutes
    - Why watch: Practice API testing with free fake API (used in Exercise 4)
    - Key topics: GET /posts, POST /posts, response validation

### Python for QA Automation

14. **Python for QA Engineers (Overview)**
    - URL: https://www.youtube.com/results?search_query=python+for+qa+engineers
    - Duration: 20-30 minutes
    - Why watch: Understand where Python fits in QA workflow
    - Key topics: Test data, API testing, test frameworks

15. **Data-Driven Testing with Python**
    - URL: https://www.youtube.com/results?search_query=data+driven+testing+python+csv
    - Duration: 25 minutes
    - Why watch: Load test data from CSV/JSON files
    - Key topics: Parameterization, test data separation

---

## 📖 Books & Reading Materials

### Python Fundamentals

1. **"Python Crash Course" by Eric Matthes** ⭐ HIGHLY RECOMMENDED
   - Publisher: No Starch Press
   - Chapters 1-5: Python basics (variables, functions, loops)
   - Why read: Beginner-friendly, practical projects
   - Free alternative: https://ehmatthes.github.io/pcc_2e/cheat_sheets/cheat_sheets/
   - **Note:** Focus on Chapters 1-5 only (rest is web development, skip for now)

2. **"Automate the Boring Stuff with Python" by Al Sweigart** ⭐ FREE ONLINE
   - URL: https://automatetheboringstuff.com/
   - Chapters 1-8: Python basics, file handling
   - Chapter 16: CSV and JSON files
   - Why read: Shows how Python saves time on repetitive tasks (QA mindset!)
   - **Bonus:** Free video course at https://www.udemy.com/course/automate/

3. **Official Python Tutorial** (FREE)
   - URL: https://docs.python.org/3/tutorial/
   - Sections 3-4: Data structures, control flow
   - Why read: Authoritative source, always up-to-date
   - **Note:** Can be dry - use as reference, not first learning resource

### Testing & QA Focus

4. **"Python Testing with pytest" by Brian Okken**
   - Publisher: Pragmatic Bookshelf
   - Chapters 1-3: pytest basics, assertions
   - Why read: Industry-standard testing framework (Week 12 preview!)
   - **Note:** Not required for Week 11, but great next step

5. **"Testing Python" by David Sale**
   - Publisher: Wiley
   - Chapter 5: Test data management
   - Chapter 7: API testing
   - Why read: QA-focused Python book (rare!)

### Online Articles & Guides

6. **Real Python - Working with Files in Python** ⭐ EXCELLENT TUTORIAL
   - URL: https://realpython.com/working-with-files-in-python/
   - Why read: Comprehensive guide to CSV, JSON, file operations
   - Free account required for some articles

7. **Real Python - API Integration in Python**
   - URL: https://realpython.com/api-integration-in-python/
   - Why read: requests library deep dive
   - Covers authentication, error handling, best practices

8. **Faker Documentation** ⭐ OFFICIAL DOCS
   - URL: https://faker.readthedocs.io/en/master/
   - Why read: Complete list of providers (fake.name(), fake.email(), etc.)
   - Browse "Providers" section to see all available data types

9. **requests Library Documentation** ⭐ OFFICIAL DOCS
   - URL: https://requests.readthedocs.io/en/latest/
   - Why read: Quickstart guide, advanced features
   - Focus on "Quickstart" section for Week 11

10. **Python CSV Module Documentation**
    - URL: https://docs.python.org/3/library/csv.html
    - Why read: Official reference for CSV operations
    - Examples: DictWriter, DictReader

11. **Python JSON Module Documentation**
    - URL: https://docs.python.org/3/library/json.html
    - Why read: Official reference for JSON operations
    - Examples: dumps(), loads(), pretty printing

---

## 🔧 Tools & Software

### Python Environment

1. **Python 3.11+** ⭐ REQUIRED
   - URL: https://www.python.org/downloads/
   - Purpose: Python interpreter
   - Free: Yes (open source)
   - Installation: Download installer for your OS
   - **CRITICAL:** Windows users check "Add Python to PATH"

2. **pip (Python Package Manager)** ⭐ INCLUDED WITH PYTHON
   - Comes with Python 3.4+
   - Purpose: Install libraries (Faker, requests)
   - Command: `pip install <package-name>`
   - Verify: `pip --version`

### Code Editors

3. **VS Code (Visual Studio Code)** ⭐ RECOMMENDED
   - URL: https://code.visualstudio.com/
   - Purpose: Code editor with Python support
   - Free: Yes
   - Extensions needed: "Python" by Microsoft
   - Why recommended: Syntax highlighting, debugging, IntelliSense

4. **PyCharm Community Edition** (Alternative)
   - URL: https://www.jetbrains.com/pycharm/download/
   - Purpose: Full-featured Python IDE
   - Free: Community edition
   - Why use: More features than VS Code, better debugging
   - **Note:** Heavier than VS Code (slower startup)

### Python Libraries (Week 11)

5. **Faker** ⭐ CRITICAL FOR WEEK 11
   - Install: `pip install faker`
   - Purpose: Generate fake test data
   - Documentation: https://faker.readthedocs.io/
   - Why use: Create 1000s of test records in seconds

6. **requests** ⭐ CRITICAL FOR WEEK 11
   - Install: `pip install requests`
   - Purpose: HTTP requests for API testing
   - Documentation: https://requests.readthedocs.io/
   - Why use: Test APIs without Postman UI

### File Viewers

7. **Microsoft Excel / Google Sheets / LibreOffice Calc**
   - Purpose: View CSV files generated by Python
   - Free: Google Sheets (web), LibreOffice (desktop)
   - Why use: Verify test data looks correct

8. **JSON Viewer Online**
   - URL: https://jsonformatter.org/json-viewer
   - Purpose: Format and validate JSON files
   - Free: Yes (web-based)
   - Why use: Check JSON structure, validate syntax

### Terminal / Command Line

9. **Windows Terminal** (Windows users)
   - URL: https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701
   - Purpose: Modern command line interface
   - Free: Yes (Microsoft Store)
   - Why use: Better than Command Prompt (multiple tabs, theming)

10. **iTerm2** (macOS users)
    - URL: https://iterm2.com/
    - Purpose: Terminal replacement for macOS
    - Free: Yes
    - Why use: Better than default Terminal app

### Version Control

11. **Git**
    - URL: https://git-scm.com/downloads
    - Purpose: Version control for Python scripts
    - Free: Yes
    - Why use: Track changes, commit code, push to GitHub

12. **GitHub Desktop** (Optional)
    - URL: https://desktop.github.com/
    - Purpose: GUI for Git
    - Free: Yes
    - Why use: Easier than command-line Git for beginners

---

## 🌐 Communities & Support

### Python Learning Communities

1. **r/learnpython** (Reddit) ⭐ BEGINNER-FRIENDLY
   - URL: https://www.reddit.com/r/learnpython/
   - Purpose: Ask Python questions, get help debugging
   - Active: Very active, responses within hours
   - Why join: Supportive community, no "stupid questions"

2. **Python Discord**
   - URL: https://pythondiscord.com/
   - Purpose: Real-time chat for Python learners
   - Active: 500K+ members, 24/7 help channels
   - Why join: Faster responses than Reddit, friendly mentors

3. **Stack Overflow - Python Tag**
   - URL: https://stackoverflow.com/questions/tagged/python
   - Purpose: Search for Python errors and solutions
   - Active: Millions of questions answered
   - Why use: 99% chance your error is already answered
   - **Tip:** Search "Python [your error message]" before posting

### QA + Python Communities

4. **Ministry of Testing - Test Automation**
   - URL: https://club.ministryoftesting.com/
   - Purpose: QA community with Python automation discussions
   - Free: Basic membership
   - Why join: QA-focused Python discussions (not generic Python)

5. **Test Automation University (TAU)** ⭐ FREE COURSES
   - URL: https://testautomationu.applitools.com/
   - Purpose: Free courses on test automation with Python
   - Courses: "Intro to Python", "API Testing with Python"
   - Why use: QA-focused, certificate upon completion

6. **Software QA & Testing StackExchange**
   - URL: https://sqa.stackexchange.com/
   - Purpose: Ask QA-specific questions
   - Active: Moderate activity, expert answers
   - Why use: QA context (not just generic programming)

### Python Official Resources

7. **Python.org Beginners Guide**
   - URL: https://www.python.org/about/gettingstarted/
   - Purpose: Official getting started guide
   - Free: Yes
   - Why use: Authoritative, always up-to-date

8. **Python Tutor (Visualize Code Execution)**
   - URL: https://pythontutor.com/
   - Purpose: Step through Python code line-by-line
   - Free: Yes
   - Why use: Understand loops, functions, variables visually
   - **HIGHLY RECOMMENDED** for beginners!

---

## 🎓 Free Online Courses

### Python Basics

1. **freeCodeCamp - Python for Beginners** ⭐ EXCELLENT FREE COURSE
   - URL: https://www.youtube.com/watch?v=rfscVS0vtbw
   - Duration: 4.5 hours (watch first 2 hours for Week 11)
   - Why take: Comprehensive, well-explained, free
   - Focus on: Variables, loops, functions, file I/O (first 2 hours)

2. **Google's Python Class** (FREE)
   - URL: https://developers.google.com/edu/python
   - Duration: 2 days (self-paced)
   - Why take: Created by Google, includes exercises
   - Focus on: Strings, lists, dictionaries, files

3. **Codecademy - Learn Python 3** (Free tier)
   - URL: https://www.codecademy.com/learn/learn-python-3
   - Duration: 25 hours (interactive)
   - Why take: Hands-on coding in browser
   - **Note:** Some content requires Pro subscription

### Python for Testing

4. **Test Automation University - Python Programming** ⭐ QA-FOCUSED
   - URL: https://testautomationu.applitools.com/python-tutorial/
   - Duration: 3 hours
   - Why take: QA context from the start
   - Certificate: Yes (free)

5. **Test Automation University - API Testing with Python**
   - URL: https://testautomationu.applitools.com/python-api-testing/
   - Duration: 2 hours
   - Why take: Covers requests library in QA context
   - Certificate: Yes (free)

6. **"Automate the Boring Stuff" Udemy Course** (FREE with code)
   - URL: https://www.udemy.com/course/automate/
   - Duration: 9.5 hours
   - Why take: Based on the book (see Books section)
   - Coupon: Often free, check https://automatetheboringstuff.com/

---

## 📊 Real-World Examples

### GitHub Repositories

1. **python-test-data-generators** ⭐ SEE REAL CODE
   - URL: https://github.com/search?q=python+test+data+generator
   - Purpose: Browse real test data generation scripts
   - Why useful: See how pros structure code
   - **Tip:** Look for repos with 50+ stars (quality indicator)

2. **requests-examples**
   - URL: https://github.com/search?q=python+requests+api+testing
   - Purpose: Real API testing examples
   - Why useful: Learn error handling, assertions, best practices

3. **faker-examples**
   - URL: https://github.com/search?q=python+faker+test+data
   - Purpose: Faker library usage patterns
   - Why useful: See edge cases, realistic data generation

### Blog Posts with Code

4. **"Generating Test Data with Python" (Real Python)**
   - URL: https://realpython.com/ (search "test data")
   - Why read: Professional examples with explanations
   - Includes: CSV, JSON, database seeding

5. **"API Testing with Python and requests" (Medium)**
   - URL: https://medium.com/search?q=python+api+testing+requests
   - Why read: Step-by-step tutorials with code
   - **Tip:** Look for articles with "pytest" (industry standard)

### Sample Projects

6. **SauceDemo Test Data Generator** (Your Week 11 Exercise 5!)
   - File: `test_data_master.py` (you'll create this)
   - Purpose: Generate checkout form test data
   - Why important: Portfolio-ready example

7. **JSONPlaceholder API Tests** (Your Week 11 Exercise 4!)
   - Files: `api_get_test.py`, `api_post_test.py`, etc.
   - Purpose: API testing examples
   - Why important: Demonstrates requests library usage

---

## 📝 Cheat Sheets & Quick References

1. **Python Cheat Sheet (Beginner)** ⭐ PRINT THIS
   - URL: https://ehmatthes.github.io/pcc_2e/cheat_sheets/cheat_sheets/
   - Purpose: Quick syntax reference (variables, loops, functions)
   - Format: PDF (printable)

2. **Faker Providers Cheat Sheet**
   - URL: https://faker.readthedocs.io/en/master/providers.html
   - Purpose: All available fake data types
   - Examples: `fake.name()`, `fake.email()`, `fake.address()`

3. **requests Library Cheat Sheet**
   - URL: https://realpython.com/python-requests/ (scroll to "Quick Reference")
   - Purpose: GET, POST, PUT, DELETE syntax
   - Examples: Headers, authentication, response parsing

4. **Python CSV Module Cheat Sheet**
   - URL: https://docs.python.org/3/library/csv.html (Examples section)
   - Purpose: Quick CSV read/write examples

5. **Python JSON Module Cheat Sheet**
   - URL: https://docs.python.org/3/library/json.html (Examples section)
   - Purpose: Quick JSON parsing examples

---

## 🚀 Next Steps After Week 11

### Week 12 Preview: Selenium Basics

- **Prerequisite:** Week 11 (Python basics, file handling, API testing)
- **What's next:** Browser automation with Selenium WebDriver
- **Why Python matters:** Selenium scripts are written in Python
- **Connection:** Week 11 test data can be loaded into Selenium tests

### Beyond QA Fundamentals

1. **pytest (Testing Framework)**
   - Learn after Week 11
   - Write professional test suites
   - Industry standard for Python testing

2. **REST API Testing (Advanced)**
   - Authentication (OAuth, JWT)
   - Performance testing with locust
   - API contract testing

3. **Database Testing with Python**
   - SQL queries with `sqlite3` or `psycopg2`
   - Validate backend data
   - Test data seeding

4. **Python for Performance Testing**
   - Load testing with locust or JMeter
   - Stress testing APIs
   - Metrics collection

---

## 💡 Tips for Using These Resources

### Time Management

- **Week 11 Tutorial**: 2-3 hours (required)
- **Week 11 Exercises**: 4-5 hours (required)
- **Supplemental videos**: 2-3 hours (optional but recommended)
- **Total time investment**: 8-11 hours for Week 11

### Learning Strategy

1. **Week 11 Tutorial FIRST**: Read tutorial.md before watching videos
2. **Watch 1-2 videos per day**: Don't binge all videos in one sitting
3. **Code along with videos**: Don't just watch - type the code yourself
4. **Bookmark docs**: Faker and requests docs are your reference guides
5. **Join 1 community**: r/learnpython or Python Discord for help

### What to Focus On

**MUST LEARN (Week 11 essentials):**
- Python installation and setup
- Variables, loops, functions
- Faker library (test data generation)
- requests library (API testing)
- CSV and JSON file handling

**NICE TO HAVE (but not required for Week 11):**
- Advanced Python features (decorators, classes)
- pytest framework (Week 12)
- Database connections
- Virtual environments (venv)

### When You Get Stuck

1. **Installation issues**: Watch OS-specific installation video (Resources #1, #2)
2. **Syntax errors**: Check Python Cheat Sheet (Cheat Sheets #1)
3. **Faker confusion**: Browse Faker Providers (Cheat Sheets #2)
4. **API testing issues**: Re-read requests docs (Reading Materials #9)
5. **General Python questions**: Ask on r/learnpython (Communities #1)

### Portfolio Building

**After Week 11, you can show:**
- `test_data_master.py` - Test data generator script
- `api_*_test.py` - API testing examples
- Generated CSV/JSON files - Professional test data format

**Interview talking points:**
- "I automated test data creation, saving 2 hours per test cycle"
- "I wrote Python scripts to test APIs without Postman"
- "I can generate 1000s of test records in seconds using Faker"

---

## 🔗 Connection to Previous Weeks

### Week 8: Test Case Design
- **Then:** You wrote 60 test cases manually
- **Now:** Python can execute those tests with different data

### Week 9: Agile Testing & BDD
- **Then:** You wrote BDD scenarios in Given-When-Then
- **Now:** Python can read test scenarios from CSV/JSON files

### Week 10: Defect Management
- **Then:** You found bugs manually in SauceDemo
- **Now:** Python can automate bug discovery (API testing)

### Week 11 → Week 12
- **Now:** You learn Python basics and API testing
- **Next:** You'll use Python to automate SauceDemo UI testing with Selenium

---

**Remember:** Week 11 is NOT about becoming a Python expert. It's about using Python to **save time on repetitive QA tasks**. Focus on practical skills: generating test data, testing APIs, handling files. Everything else is bonus! 🚀
