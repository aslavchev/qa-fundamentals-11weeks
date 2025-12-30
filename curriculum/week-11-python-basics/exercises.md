# Week 11: Python for Test Data & APIs - Exercises

## 📋 Exercise Overview

This week focuses on **practical Python for QA tasks**. You'll automate test data creation, handle files, and perform simple API testing - all without touching Selenium or UI automation.

**Total Time:** 4-5 hours
**Deliverables:** 5 markdown files + Python scripts in `mentee-work/week-11/`

**Important:** This is NOT a comprehensive Python course. We're learning just enough Python to save time on repetitive QA tasks.

---

## Exercise 1: Python Setup & First Script (30 min)

### Objective
Install Python development environment and verify it works

### Why This Matters
Before you can automate anything, you need a working Python installation. This exercise ensures your environment is ready for Week 11 exercises.

---

### Instructions

#### Step 1: Install Python (10 min)

**Follow the installation guide for your OS:**

**Windows:**
1. Go to https://www.python.org/downloads/
2. Download Python 3.11+ (latest stable version)
3. Run installer
   - **CRITICAL:** ✅ Check "Add Python to PATH"
   - Click "Install Now"
4. Verify installation:
   ```bash
   python --version
   ```
   Should show: `Python 3.11.x` or higher

**macOS:**
```bash
# Using Homebrew (recommended)
brew install python3

# Verify
python3 --version
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt update
sudo apt install python3 python3-pip

# Verify
python3 --version
pip3 --version
```

---

#### Step 2: Install VS Code + Python Extension (10 min)

1. **Download VS Code:** https://code.visualstudio.com/
2. **Install Python extension:**
   - Open VS Code
   - Click Extensions icon (left sidebar)
   - Search "Python"
   - Install "Python" by Microsoft
3. **Verify extension:**
   - Create new file: `test.py`
   - Type: `print("Hello")`
   - Should see syntax highlighting

---

#### Step 3: Create Your First Python Script (10 min)

**What You'll Build:** A script that prints system info

**Create file:** `mentee-work/week-11/hello_qa.py`

```python
# hello_qa.py
# My first Python script for QA

print("=" * 50)
print("QA AUTOMATION ENVIRONMENT CHECK")
print("=" * 50)

# Check Python version
import sys
print(f"\nPython Version: {sys.version}")

# Check platform
import platform
print(f"Operating System: {platform.system()} {platform.release()}")

# Test basic data types
username = "standard_user"
test_count = 60
passed = True

print(f"\nTest Data:")
print(f"  Username: {username}")
print(f"  Test Cases: {test_count}")
print(f"  All Passed: {passed}")

print("\n✅ Python environment is ready for QA automation!")
```

**Run it:**
```bash
cd mentee-work/week-11
python hello_qa.py
```

**Expected output:**
```
==================================================
QA AUTOMATION ENVIRONMENT CHECK
==================================================

Python Version: 3.11.5 (main, ...)
Operating System: Windows 10

Test Data:
  Username: standard_user
  Test Cases: 60
  All Passed: True

✅ Python environment is ready for QA automation!
```

---

#### Step 4: Install Required Libraries (5 min)

**What You'll Install:**
- `requests` - For API testing
- `faker` - For generating fake test data

**Run these commands:**
```bash
pip install requests faker

# Verify installation
pip list | grep requests
pip list | grep Faker
```

**Test installation:**
```python
# test_imports.py
import requests
import faker

print("✅ requests library installed")
print("✅ faker library installed")
print("\nReady for Week 11 exercises!")
```

---

### Common Mistakes

❌ **"Python is not recognized as a command"**
- Fix: Didn't check "Add Python to PATH" during installation
- Solution: Reinstall Python with PATH checkbox checked

❌ **"pip is not recognized"**
- Fix: pip wasn't installed with Python
- Solution: Run `python -m ensurepip` or reinstall Python

❌ **"ModuleNotFoundError: No module named 'requests'"**
- Fix: Didn't run `pip install requests`
- Solution: Install the library first before importing

---

### Deliverable Format

Save as `mentee-work/week-11/python-setup.md`

```markdown
# Week 11 - Exercise 1: Python Setup

**Your Name:** [Your name]
**Date:** [Date]
**OS:** [Windows / macOS / Linux]

---

## Installation Verification

### Python Version
```
[Paste output of: python --version]
```

### Pip Version
```
[Paste output of: pip --version]
```

### VS Code + Python Extension
- [ ] VS Code installed
- [ ] Python extension installed
- [ ] Syntax highlighting works

---

## hello_qa.py Output

```
[Paste full output of running hello_qa.py]
```

---

## Libraries Installed

```
[Paste output of: pip list | grep -E 'requests|Faker']
```

---

## Troubleshooting (if any)

**Issues encountered:**
[Describe any problems you faced and how you solved them]

**Time spent:** [X minutes]

---

## Environment Ready ✅

- [ ] Python 3.11+ installed
- [ ] pip working
- [ ] VS Code + Python extension installed
- [ ] requests library installed
- [ ] faker library installed
- [ ] hello_qa.py runs successfully
```

---

### Success Criteria

- ✅ Python 3.11+ installed and in PATH
- ✅ pip working
- ✅ VS Code with Python extension installed
- ✅ hello_qa.py runs without errors
- ✅ requests and faker libraries installed

---

## Exercise 2: Test Data Generator (60 min)

### Objective
Create a Python script that generates 50 checkout test data records in seconds

### Why This Matters
**Manual way:** Typing 50 sets of (First Name, Last Name, Zip Code) takes 2 hours and is error-prone.

**Python way:** Generate 50 random test data records in 5 seconds with this script. This is a real QA time-saver.

---

### Instructions

#### Step 1: Understand the Problem (5 min)

**SauceDemo Checkout Form requires:**
- First Name
- Last Name
- Zip Code

**Manual testing problem:**
- Need to test with different data (not just "John", "Doe", "12345" every time)
- Need edge cases: long names, short names, special characters
- Need volume: 50+ test cases

**Python solution:** Generate realistic random test data automatically.

---

#### Step 2: Learn Faker Library Basics (10 min)

**What is Faker?**
A Python library that generates realistic fake data (names, addresses, emails, etc.)

**Try it yourself:**

Create `test_faker.py`:
```python
from faker import Faker

# Create a Faker instance
fake = Faker()

# Generate random data
print("First Name:", fake.first_name())
print("Last Name:", fake.last_name())
print("Zip Code:", fake.zipcode())
print("Full Address:", fake.address())
print("Email:", fake.email())

# Run it 3 times - different data each time!
```

**Run it:**
```bash
python test_faker.py
```

**What happens:** Each time you run it, you get different data. That's the power of randomization!

---

#### Step 3: Build Checkout Data Generator (30 min)

**What You'll Build:** Script that generates 50 checkout test data records

**Create file:** `mentee-work/week-11/checkout_data_generator.py`

```python
# checkout_data_generator.py
# Generates test data for SauceDemo checkout form

from faker import Faker

# Initialize Faker
fake = Faker()

# Set random seed for reproducibility (optional)
# Faker.seed(12345)  # Uncomment to get same data every run

def generate_checkout_data(count=50):
    """
    Generate test data for SauceDemo checkout form

    Args:
        count: Number of test data records to generate

    Returns:
        List of tuples (first_name, last_name, zip_code)
    """
    test_data = []

    for i in range(count):
        first_name = fake.first_name()
        last_name = fake.last_name()
        zip_code = fake.zipcode()

        test_data.append((first_name, last_name, zip_code))

    return test_data

# Main execution
if __name__ == "__main__":
    print("=" * 60)
    print("SAUCEDEMO CHECKOUT TEST DATA GENERATOR")
    print("=" * 60)

    # Generate 50 test data records
    data = generate_checkout_data(50)

    # Display results
    print(f"\nGenerated {len(data)} test data records:\n")
    print(f"{'#':<5} {'First Name':<15} {'Last Name':<15} {'Zip Code':<10}")
    print("-" * 60)

    for i, (first, last, zip_code) in enumerate(data, 1):
        print(f"{i:<5} {first:<15} {last:<15} {zip_code:<10}")

    print("\n✅ Test data generation complete!")
    print(f"💾 Ready to use for {len(data)} checkout tests")
```

**Run it:**
```bash
python checkout_data_generator.py
```

**Expected output:**
```
============================================================
SAUCEDEMO CHECKOUT TEST DATA GENERATOR
============================================================

Generated 50 test data records:

#     First Name      Last Name       Zip Code
------------------------------------------------------------
1     John            Smith           90210
2     Maria           Garcia          10001
3     David           Johnson         60614
...
50    Sarah           Williams        33101

✅ Test data generation complete!
💾 Ready to use for 50 checkout tests
```

---

#### Step 4: Add Edge Cases (10 min)

**Problem:** Faker generates normal data. QA needs edge cases too!

**Add these functions to your script:**

```python
def generate_edge_cases():
    """Generate edge case test data"""
    edge_cases = [
        # Empty fields (will be handled separately in testing)
        # ("", "", ""),  # All empty

        # Minimum length
        ("A", "B", "12345"),

        # Maximum length (100 characters)
        ("A" * 100, "B" * 100, "99999"),

        # Special characters
        ("John-Paul", "O'Brien", "12345"),
        ("María", "José", "90210"),

        # Numbers in names (should this be allowed?)
        ("John123", "Doe456", "12345"),

        # Spaces
        ("John Paul", "Van Der Berg", "12345"),

        # Unicode characters
        ("François", "Müller", "12345"),
        ("北京", "东京", "12345"),
    ]

    return edge_cases

# In main execution, add:
edge_data = generate_edge_cases()
print(f"\n📋 Edge Cases ({len(edge_data)} records):")
for i, (first, last, zip_code) in enumerate(edge_data, 1):
    print(f"{i:<5} {first:<15} {last:<15} {zip_code:<10}")
```

---

#### Step 5: Self-Review (5 min)

**Run your script and verify:**
- [ ] Generates 50 records without errors
- [ ] Each record has first name, last name, zip code
- [ ] Data is different each time (unless seed set)
- [ ] Edge cases included
- [ ] Output is readable

---

### Common Mistakes

❌ **"NameError: name 'fake' is not defined"**
- Forgot to create Faker instance: `fake = Faker()`

❌ **"TypeError: 'Faker' object is not callable"**
- Wrote `fake.first_name` instead of `fake.first_name()` (missing parentheses)

❌ **"IndexError: tuple index out of range"**
- Tried to access data wrong way - tuples are indexed (0, 1, 2)

---

### Deliverable Format

Save as `mentee-work/week-11/test-data-generator.md`

```markdown
# Week 11 - Exercise 2: Test Data Generator

**Your Name:** [Your name]
**Date:** [Date]

---

## Script Output

```
[Paste full output of checkout_data_generator.py showing all 50 records]
```

---

## Edge Cases Generated

```
[Paste edge cases output]
```

---

## Code Explanation

**What does `fake.first_name()` do?**
[Your explanation in plain English]

**Why use a loop `for i in range(count)`?**
[Your explanation]

**What is a tuple `(first_name, last_name, zip_code)`?**
[Your explanation]

---

## Real QA Use Case

**Time saved:**
- Manual: [X] hours to create 50 test data sets
- Python: [X] seconds with this script
- **Savings:** [X] hours

**How I would use this in real testing:**
[Describe how you'd integrate this into your test workflow]

---

## Reflection

**What was challenging?**
[Your answer]

**What will you use this for?**
[Your answer - e.g., "Generate test data for login forms, registration forms, etc."]
```

---

### Success Criteria

- ✅ Script generates 50 test data records
- ✅ Each record has 3 fields (first, last, zip)
- ✅ Data is randomized (different each run)
- ✅ Edge cases included (8+ cases)
- ✅ Output is formatted and readable
- ✅ Script runs without errors

---

## Exercise 3: CSV/JSON File Handling (60 min)

### Objective
Save generated test data to CSV and JSON files for reuse

### Why This Matters
Generating data is great, but you need to **save it** so you can:
- Use it across multiple test sessions
- Share it with team members
- Import it into test management tools
- Track which data was used for which test run

---

### Instructions

#### Step 1: Save Test Data to CSV (20 min)

**What You'll Build:** Script that saves test data to CSV file

**Create file:** `mentee-work/week-11/save_to_csv.py`

```python
# save_to_csv.py
# Save test data to CSV file

import csv
from faker import Faker

fake = Faker()

def generate_test_data(count=50):
    """Generate test data"""
    data = []
    for i in range(count):
        data.append({
            'test_id': f'TC-CHECKOUT-{i+1:03d}',  # TC-CHECKOUT-001, TC-CHECKOUT-002, ...
            'first_name': fake.first_name(),
            'last_name': fake.last_name(),
            'zip_code': fake.zipcode(),
            'expected_result': 'Order placed successfully'
        })
    return data

def save_to_csv(data, filename='checkout_test_data.csv'):
    """
    Save test data to CSV file

    Args:
        data: List of dictionaries
        filename: Output CSV filename
    """
    # Define CSV columns
    fieldnames = ['test_id', 'first_name', 'last_name', 'zip_code', 'expected_result']

    # Write to CSV
    with open(filename, 'w', newline='') as csvfile:
        writer = csv.DictWriter(csvfile, fieldnames=fieldnames)

        # Write header row
        writer.writeheader()

        # Write data rows
        writer.writerows(data)

    print(f"✅ Saved {len(data)} records to {filename}")

# Main execution
if __name__ == "__main__":
    print("Generating test data...")
    test_data = generate_test_data(50)

    print("Saving to CSV...")
    save_to_csv(test_data)

    print("\n✅ CSV file created successfully!")
    print("📂 Open 'checkout_test_data.csv' in Excel or text editor")
```

**Run it:**
```bash
python save_to_csv.py
```

**Verify:**
Open `checkout_test_data.csv` in Excel or text editor. Should look like:

```csv
test_id,first_name,last_name,zip_code,expected_result
TC-CHECKOUT-001,John,Smith,90210,Order placed successfully
TC-CHECKOUT-002,Maria,Garcia,10001,Order placed successfully
...
```

---

#### Step 2: Read Data from CSV (15 min)

**What You'll Build:** Script that reads CSV and prints test data

**Create file:** `mentee-work/week-11/read_from_csv.py`

```python
# read_from_csv.py
# Read test data from CSV file

import csv

def read_csv(filename='checkout_test_data.csv'):
    """
    Read test data from CSV file

    Returns:
        List of dictionaries
    """
    data = []

    with open(filename, 'r') as csvfile:
        reader = csv.DictReader(csvfile)

        for row in reader:
            data.append(row)

    return data

# Main execution
if __name__ == "__main__":
    print("Reading test data from CSV...\n")

    test_data = read_csv()

    print(f"Loaded {len(test_data)} test cases:\n")
    print(f"{'Test ID':<20} {'Name':<30} {'Zip':<10}")
    print("-" * 60)

    for record in test_data:
        full_name = f"{record['first_name']} {record['last_name']}"
        print(f"{record['test_id']:<20} {full_name:<30} {record['zip_code']:<10}")

    print(f"\n✅ Successfully read {len(test_data)} records from CSV")
```

**Run it:**
```bash
python read_from_csv.py
```

---

#### Step 3: Save Test Data to JSON (15 min)

**What is JSON?**
JavaScript Object Notation - a format for storing structured data. APIs use JSON a lot!

**Create file:** `mentee-work/week-11/save_to_json.py`

```python
# save_to_json.py
# Save test data to JSON file

import json
from faker import Faker

fake = Faker()

def generate_test_data(count=50):
    """Generate test data"""
    data = []
    for i in range(count):
        data.append({
            'testId': f'TC-CHECKOUT-{i+1:03d}',
            'firstName': fake.first_name(),
            'lastName': fake.last_name(),
            'zipCode': fake.zipcode(),
            'expectedResult': 'Order placed successfully',
            'priority': 'P2',
            'module': 'Checkout'
        })
    return data

def save_to_json(data, filename='checkout_test_data.json'):
    """Save test data to JSON file"""

    with open(filename, 'w') as jsonfile:
        json.dump(data, jsonfile, indent=2)  # indent=2 makes it readable

    print(f"✅ Saved {len(data)} records to {filename}")

# Main execution
if __name__ == "__main__":
    print("Generating test data...")
    test_data = generate_test_data(50)

    print("Saving to JSON...")
    save_to_json(test_data)

    print("\n✅ JSON file created successfully!")
    print("📂 Open 'checkout_test_data.json' in text editor or browser")
```

**Run it:**
```bash
python save_to_json.py
```

**Verify:**
Open `checkout_test_data.json`. Should look like:

```json
[
  {
    "testId": "TC-CHECKOUT-001",
    "firstName": "John",
    "lastName": "Smith",
    "zipCode": "90210",
    "expectedResult": "Order placed successfully",
    "priority": "P2",
    "module": "Checkout"
  },
  ...
]
```

---

#### Step 4: Read Data from JSON (10 min)

**Create file:** `mentee-work/week-11/read_from_json.py`

```python
# read_from_json.py
# Read test data from JSON file

import json

def read_json(filename='checkout_test_data.json'):
    """Read test data from JSON file"""

    with open(filename, 'r') as jsonfile:
        data = json.load(jsonfile)

    return data

# Main execution
if __name__ == "__main__":
    print("Reading test data from JSON...\n")

    test_data = read_json()

    print(f"Loaded {len(test_data)} test cases:\n")

    # Show first 5 records
    for record in test_data[:5]:
        print(f"Test ID: {record['testId']}")
        print(f"  Name: {record['firstName']} {record['lastName']}")
        print(f"  Zip: {record['zipCode']}")
        print(f"  Priority: {record['priority']}")
        print()

    print(f"✅ Successfully read {len(test_data)} records from JSON")
```

**Run it:**
```bash
python read_from_json.py
```

---

### Common Mistakes

❌ **"FileNotFoundError: [Errno 2] No such file or directory"**
- Trying to read file that doesn't exist
- Solution: Run save script first, or check filename spelling

❌ **"json.decoder.JSONDecodeError: Expecting value"**
- JSON file is empty or corrupted
- Solution: Regenerate the JSON file

❌ **"KeyError: 'first_name'"**
- Typo in dictionary key
- Solution: Check exact spelling (case-sensitive!)

---

### Deliverable Format

Save as `mentee-work/week-11/csv-json-handling.md`

```markdown
# Week 11 - Exercise 3: CSV/JSON File Handling

**Your Name:** [Your name]
**Date:** [Date]

---

## Files Created

- [ ] checkout_test_data.csv (50 records)
- [ ] checkout_test_data.json (50 records)
- [ ] save_to_csv.py (working)
- [ ] read_from_csv.py (working)
- [ ] save_to_json.py (working)
- [ ] read_from_json.py (working)

---

## CSV Output Sample

```
[Paste first 10 rows of CSV file]
```

---

## JSON Output Sample

```json
[Paste first 2 test case records from JSON file]
```

---

## Read CSV Output

```
[Paste output of read_from_csv.py]
```

---

## Read JSON Output

```
[Paste output of read_from_json.py]
```

---

## Real QA Use Case

**CSV vs JSON - When to use which?**

**CSV:**
- [Your answer - e.g., "Import into Excel, share with non-technical team"]

**JSON:**
- [Your answer - e.g., "API testing, pass data to automated tests"]

**How I would use these files in real testing:**
[Your workflow description]

---

## Code Explanation

**What does `csv.DictWriter(csvfile, fieldnames=fieldnames)` do?**
[Your explanation]

**What does `json.dump(data, jsonfile, indent=2)` do?**
[Your explanation]

**Why use `with open(filename, 'w') as csvfile:`?**
[Your explanation - hint: automatic file closing]
```

---

### Success Criteria

- ✅ CSV file created with 50 test records
- ✅ JSON file created with 50 test records
- ✅ Read CSV script displays data correctly
- ✅ Read JSON script displays data correctly
- ✅ All files committed to GitHub
- ✅ Can explain when to use CSV vs JSON

---

## Exercise 4: Simple API Testing (60 min)

### Objective
Test a public API using Python requests library

### Why This Matters
**Not all testing needs a UI!** APIs are:
- Faster to test (no browser needed)
- More reliable (no UI flakiness)
- Easier to automate

This exercise teaches basic API testing - a critical QA skill.

---

### Instructions

#### Step 1: Understand HTTP Requests (10 min)

**What is an API?**
Application Programming Interface - a way for software to talk to software (no UI needed).

**HTTP Methods:**
- `GET` - Retrieve data (like searching)
- `POST` - Create new data (like submitting a form)
- `PUT` - Update existing data
- `DELETE` - Delete data

**We'll test:** https://jsonplaceholder.typicode.com (fake API for testing)

**Try this in your browser:**
https://jsonplaceholder.typicode.com/posts/1

You should see JSON response with a blog post.

---

#### Step 2: Test GET Request (15 min)

**What You'll Build:** Script that tests GET request

**Create file:** `mentee-work/week-11/api_get_test.py`

```python
# api_get_test.py
# Test API GET request

import requests
import json

def test_get_post():
    """Test GET /posts/1 endpoint"""

    print("=" * 60)
    print("API TEST: GET /posts/1")
    print("=" * 60)

    # Make GET request
    url = "https://jsonplaceholder.typicode.com/posts/1"
    response = requests.get(url)

    # Check status code
    print(f"\n✓ Status Code: {response.status_code}")
    assert response.status_code == 200, "Expected 200 OK"

    # Parse JSON response
    data = response.json()

    # Verify response structure
    print(f"✓ Response is JSON: {type(data)}")
    assert 'userId' in data, "Missing 'userId' field"
    assert 'id' in data, "Missing 'id' field"
    assert 'title' in data, "Missing 'title' field"
    assert 'body' in data, "Missing 'body' field"

    # Verify data values
    print(f"✓ Post ID: {data['id']}")
    assert data['id'] == 1, "Expected post ID = 1"

    print(f"✓ User ID: {data['userId']}")
    assert data['userId'] == 1, "Expected user ID = 1"

    print(f"✓ Title: {data['title'][:50]}...")
    assert len(data['title']) > 0, "Title should not be empty"

    print(f"✓ Body: {data['body'][:50]}...")
    assert len(data['body']) > 0, "Body should not be empty"

    print("\n" + "=" * 60)
    print("✅ TEST PASSED: GET /posts/1")
    print("=" * 60)

# Run test
if __name__ == "__main__":
    test_get_post()
```

**Run it:**
```bash
python api_get_test.py
```

**Expected output:**
```
============================================================
API TEST: GET /posts/1
============================================================

✓ Status Code: 200
✓ Response is JSON: <class 'dict'>
✓ Post ID: 1
✓ User ID: 1
✓ Title: sunt aut facere repellat provident occaecati...
✓ Body: quia et suscipit\nsuscipit recusandae consequuntur...

============================================================
✅ TEST PASSED: GET /posts/1
============================================================
```

---

#### Step 3: Test POST Request (15 min)

**What You'll Build:** Script that creates a new post via API

**Create file:** `mentee-work/week-11/api_post_test.py`

```python
# api_post_test.py
# Test API POST request

import requests

def test_create_post():
    """Test POST /posts endpoint"""

    print("=" * 60)
    print("API TEST: POST /posts (Create New Post)")
    print("=" * 60)

    # Prepare request data
    url = "https://jsonplaceholder.typicode.com/posts"
    new_post = {
        'userId': 1,
        'title': 'QA Test Post - Automated',
        'body': 'This post was created by Python API test'
    }

    print(f"\n📤 Sending POST request...")
    print(f"   URL: {url}")
    print(f"   Data: {new_post}")

    # Make POST request
    response = requests.post(url, json=new_post)

    # Check status code (201 Created)
    print(f"\n✓ Status Code: {response.status_code}")
    assert response.status_code == 201, "Expected 201 Created"

    # Parse response
    created_post = response.json()

    # Verify response
    print(f"✓ Created Post ID: {created_post['id']}")
    assert 'id' in created_post, "Response should include new post ID"

    print(f"✓ Title: {created_post['title']}")
    assert created_post['title'] == new_post['title'], "Title mismatch"

    print(f"✓ Body: {created_post['body']}")
    assert created_post['body'] == new_post['body'], "Body mismatch"

    print("\n" + "=" * 60)
    print("✅ TEST PASSED: POST /posts")
    print("=" * 60)

# Run test
if __name__ == "__main__":
    test_create_post()
```

**Run it:**
```bash
python api_post_test.py
```

---

#### Step 4: Test Error Scenarios (15 min)

**What You'll Build:** Script that tests error handling

**Create file:** `mentee-work/week-11/api_error_test.py`

```python
# api_error_test.py
# Test API error scenarios

import requests

def test_not_found():
    """Test 404 Not Found"""

    print("\n" + "=" * 60)
    print("API TEST: 404 Not Found")
    print("=" * 60)

    # Request non-existent post
    url = "https://jsonplaceholder.typicode.com/posts/99999"
    response = requests.get(url)

    print(f"\n✓ Status Code: {response.status_code}")
    assert response.status_code == 404, "Expected 404 Not Found"

    print("✅ TEST PASSED: 404 handled correctly")

def test_invalid_endpoint():
    """Test invalid endpoint"""

    print("\n" + "=" * 60)
    print("API TEST: Invalid Endpoint")
    print("=" * 60)

    # Request invalid endpoint
    url = "https://jsonplaceholder.typicode.com/invalid"
    response = requests.get(url)

    print(f"\n✓ Status Code: {response.status_code}")
    assert response.status_code == 404, "Expected 404 for invalid endpoint"

    print("✅ TEST PASSED: Invalid endpoint handled")

def test_response_time():
    """Test API response time"""

    print("\n" + "=" * 60)
    print("API TEST: Response Time")
    print("=" * 60)

    url = "https://jsonplaceholder.typicode.com/posts/1"
    response = requests.get(url)

    # Check response time (should be < 2 seconds)
    elapsed_ms = response.elapsed.total_seconds() * 1000
    print(f"\n✓ Response Time: {elapsed_ms:.2f} ms")
    assert elapsed_ms < 2000, "Response time should be < 2 seconds"

    print("✅ TEST PASSED: Response time acceptable")

# Run all tests
if __name__ == "__main__":
    test_not_found()
    test_invalid_endpoint()
    test_response_time()

    print("\n" + "=" * 60)
    print("✅ ALL API ERROR TESTS PASSED")
    print("=" * 60)
```

**Run it:**
```bash
python api_error_test.py
```

---

#### Step 5: Create API Test Report (5 min)

**Create file:** `mentee-work/week-11/api_test_suite.py`

```python
# api_test_suite.py
# Complete API test suite with reporting

import requests
import time

class APITestSuite:
    def __init__(self):
        self.base_url = "https://jsonplaceholder.typicode.com"
        self.results = []

    def run_test(self, test_name, test_func):
        """Run a single test and record result"""
        try:
            start_time = time.time()
            test_func()
            elapsed = time.time() - start_time
            self.results.append({
                'name': test_name,
                'status': 'PASS',
                'time': f"{elapsed:.2f}s"
            })
            print(f"✅ {test_name}: PASS ({elapsed:.2f}s)")
        except AssertionError as e:
            self.results.append({
                'name': test_name,
                'status': 'FAIL',
                'error': str(e)
            })
            print(f"❌ {test_name}: FAIL - {e}")

    def test_get_single_post(self):
        """GET /posts/1"""
        response = requests.get(f"{self.base_url}/posts/1")
        assert response.status_code == 200
        assert 'title' in response.json()

    def test_get_all_posts(self):
        """GET /posts"""
        response = requests.get(f"{self.base_url}/posts")
        assert response.status_code == 200
        assert len(response.json()) > 0

    def test_create_post(self):
        """POST /posts"""
        data = {'userId': 1, 'title': 'Test', 'body': 'Test body'}
        response = requests.post(f"{self.base_url}/posts", json=data)
        assert response.status_code == 201

    def test_not_found(self):
        """GET /posts/99999 (404)"""
        response = requests.get(f"{self.base_url}/posts/99999")
        assert response.status_code == 404

    def run_all(self):
        """Run all tests"""
        print("=" * 60)
        print("API TEST SUITE")
        print("=" * 60)

        self.run_test("GET /posts/1", self.test_get_single_post)
        self.run_test("GET /posts", self.test_get_all_posts)
        self.run_test("POST /posts", self.test_create_post)
        self.run_test("404 Handling", self.test_not_found)

        # Print summary
        print("\n" + "=" * 60)
        print("TEST SUMMARY")
        print("=" * 60)
        passed = sum(1 for r in self.results if r['status'] == 'PASS')
        failed = len(self.results) - passed
        print(f"Total: {len(self.results)} | Passed: {passed} | Failed: {failed}")
        print("=" * 60)

# Run test suite
if __name__ == "__main__":
    suite = APITestSuite()
    suite.run_all()
```

**Run it:**
```bash
python api_test_suite.py
```

---

### Common Mistakes

❌ **"ConnectionError: Failed to establish a new connection"**
- No internet connection or API is down
- Solution: Check internet, try different API

❌ **"AssertionError: Expected 200 OK"**
- API returned different status code
- Solution: Print `response.status_code` to see actual value

❌ **"KeyError: 'title'"**
- JSON response doesn't have expected field
- Solution: Print `response.json()` to see actual structure

---

### Deliverable Format

Save as `mentee-work/week-11/simple-api-testing.md`

```markdown
# Week 11 - Exercise 4: Simple API Testing

**Your Name:** [Your name]
**Date:** [Date]

---

## Test Results

### GET /posts/1

```
[Paste output of api_get_test.py]
```

### POST /posts

```
[Paste output of api_post_test.py]
```

### Error Scenarios

```
[Paste output of api_error_test.py]
```

### Full Test Suite

```
[Paste output of api_test_suite.py]
```

---

## API vs UI Testing

**Advantages of API testing:**
1. [Your answer]
2. [Your answer]
3. [Your answer]

**When would you use API testing instead of UI testing?**
[Your answer]

---

## Code Explanation

**What does `response = requests.get(url)` do?**
[Your explanation]

**What does `response.json()` do?**
[Your explanation]

**What is the difference between status code 200 and 201?**
[Your answer]

---

## Real QA Use Case

**How would you use this for SauceDemo?**
[Your answer - Note: SauceDemo doesn't have an API, but if it did...]

**What APIs would you test in a real e-commerce app?**
- [Example 1]
- [Example 2]
- [Example 3]
```

---

### Success Criteria

- ✅ GET request test passes
- ✅ POST request test passes
- ✅ Error scenarios tested (404, invalid endpoint)
- ✅ Response time validated (< 2 seconds)
- ✅ Test suite runs all tests and reports results
- ✅ Can explain difference between GET and POST

---

## Exercise 5: Complete Test Data Script (45 min)

### Objective
Build a comprehensive test data generation script that combines everything learned

### Why This Matters
This is your **Week 11 capstone** - a production-ready script you can actually use in real QA work.

---

### Instructions

#### Step 1: Plan Your Script (5 min)

**What it should do:**
1. Generate 50 random test data records
2. Add 10 edge cases
3. Save to both CSV and JSON
4. Print summary report

**Script name:** `test_data_master.py`

---

#### Step 2: Build Complete Script (30 min)

**Create file:** `mentee-work/week-11/test_data_master.py`

```python
# test_data_master.py
# Complete test data generation solution for SauceDemo checkout

import csv
import json
from faker import Faker
from datetime import datetime

# Initialize Faker
fake = Faker()

def generate_random_data(count=50):
    """Generate random test data"""
    data = []
    for i in range(count):
        data.append({
            'test_id': f'TC-CHECKOUT-{i+1:03d}',
            'category': 'Random',
            'first_name': fake.first_name(),
            'last_name': fake.last_name(),
            'zip_code': fake.zipcode(),
            'expected_result': 'Order placed successfully',
            'priority': 'P2',
            'status': 'Not Executed'
        })
    return data

def generate_edge_cases():
    """Generate edge case test data"""
    edge_cases = [
        {
            'test_id': 'TC-CHECKOUT-EDGE-001',
            'category': 'Edge Case',
            'first_name': 'A',
            'last_name': 'B',
            'zip_code': '12345',
            'expected_result': 'Order placed successfully',
            'priority': 'P1',
            'status': 'Not Executed'
        },
        {
            'test_id': 'TC-CHECKOUT-EDGE-002',
            'category': 'Edge Case',
            'first_name': 'A' * 100,
            'last_name': 'B' * 100,
            'zip_code': '99999',
            'expected_result': 'Order placed successfully',
            'priority': 'P1',
            'status': 'Not Executed'
        },
        {
            'test_id': 'TC-CHECKOUT-EDGE-003',
            'category': 'Edge Case',
            'first_name': 'John-Paul',
            'last_name': "O'Brien",
            'zip_code': '12345',
            'expected_result': 'Order placed successfully',
            'priority': 'P2',
            'status': 'Not Executed'
        },
        {
            'test_id': 'TC-CHECKOUT-EDGE-004',
            'category': 'Edge Case',
            'first_name': 'María',
            'last_name': 'José',
            'zip_code': '90210',
            'expected_result': 'Order placed successfully',
            'priority': 'P2',
            'status': 'Not Executed'
        },
        {
            'test_id': 'TC-CHECKOUT-EDGE-005',
            'category': 'Edge Case',
            'first_name': 'John Paul',
            'last_name': 'Van Der Berg',
            'zip_code': '12345',
            'expected_result': 'Order placed successfully',
            'priority': 'P2',
            'status': 'Not Executed'
        },
        {
            'test_id': 'TC-CHECKOUT-EDGE-006',
            'category': 'Edge Case',
            'first_name': 'François',
            'last_name': 'Müller',
            'zip_code': '12345',
            'expected_result': 'Order placed successfully',
            'priority': 'P2',
            'status': 'Not Executed'
        },
        {
            'test_id': 'TC-CHECKOUT-EDGE-007',
            'category': 'Edge Case',
            'first_name': '北京',
            'last_name': '东京',
            'zip_code': '12345',
            'expected_result': 'Error: Invalid characters',
            'priority': 'P2',
            'status': 'Not Executed'
        },
        {
            'test_id': 'TC-CHECKOUT-EDGE-008',
            'category': 'Edge Case',
            'first_name': 'John123',
            'last_name': 'Doe456',
            'zip_code': '12345',
            'expected_result': 'Error: Numbers not allowed',
            'priority': 'P2',
            'status': 'Not Executed'
        },
        {
            'test_id': 'TC-CHECKOUT-EDGE-009',
            'category': 'Edge Case',
            'first_name': '',
            'last_name': 'Doe',
            'zip_code': '12345',
            'expected_result': 'Error: First Name is required',
            'priority': 'P1',
            'status': 'Not Executed'
        },
        {
            'test_id': 'TC-CHECKOUT-EDGE-010',
            'category': 'Edge Case',
            'first_name': 'John',
            'last_name': '',
            'zip_code': '12345',
            'expected_result': 'Error: Last Name is required',
            'priority': 'P1',
            'status': 'Not Executed'
        },
    ]
    return edge_cases

def save_to_csv(data, filename='saucedemo_checkout_tests.csv'):
    """Save data to CSV"""
    fieldnames = ['test_id', 'category', 'first_name', 'last_name', 'zip_code',
                  'expected_result', 'priority', 'status']

    with open(filename, 'w', newline='', encoding='utf-8') as csvfile:
        writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
        writer.writeheader()
        writer.writerows(data)

    print(f"✅ CSV: Saved {len(data)} records to {filename}")

def save_to_json(data, filename='saucedemo_checkout_tests.json'):
    """Save data to JSON"""

    # Add metadata
    output = {
        'metadata': {
            'generated_at': datetime.now().isoformat(),
            'total_tests': len(data),
            'generator': 'test_data_master.py',
            'application': 'SauceDemo',
            'module': 'Checkout'
        },
        'tests': data
    }

    with open(filename, 'w', encoding='utf-8') as jsonfile:
        json.dump(output, jsonfile, indent=2, ensure_ascii=False)

    print(f"✅ JSON: Saved {len(data)} records to {filename}")

def print_summary(random_data, edge_data):
    """Print generation summary"""
    total = len(random_data) + len(edge_data)

    print("\n" + "=" * 70)
    print("SAUCEDEMO CHECKOUT TEST DATA - GENERATION SUMMARY")
    print("=" * 70)
    print(f"\n📊 Statistics:")
    print(f"   Random Test Cases: {len(random_data)}")
    print(f"   Edge Cases: {len(edge_data)}")
    print(f"   Total: {total}")

    print(f"\n📋 Categories:")
    print(f"   P1 (High Priority): {sum(1 for d in edge_data if d['priority'] == 'P1')}")
    print(f"   P2 (Medium Priority): {total - sum(1 for d in edge_data if d['priority'] == 'P1')}")

    print(f"\n💾 Files Created:")
    print(f"   saucedemo_checkout_tests.csv")
    print(f"   saucedemo_checkout_tests.json")

    print(f"\n✅ Ready for testing!")
    print("=" * 70)

# Main execution
if __name__ == "__main__":
    print("Generating SauceDemo checkout test data...\n")

    # Generate data
    random_data = generate_random_data(50)
    edge_data = generate_edge_cases()

    # Combine all data
    all_data = random_data + edge_data

    # Save to files
    save_to_csv(all_data)
    save_to_json(all_data)

    # Print summary
    print_summary(random_data, edge_data)
```

**Run it:**
```bash
python test_data_master.py
```

---

#### Step 3: Verify Output (5 min)

**Check that files were created:**
- [ ] `saucedemo_checkout_tests.csv` exists
- [ ] `saucedemo_checkout_tests.json` exists
- [ ] CSV has 60 rows (50 random + 10 edge)
- [ ] JSON has metadata section

---

#### Step 4: Test the Data (5 min)

**Read the files to verify:**

```python
# verify_data.py
import csv
import json

# Read CSV
with open('saucedemo_checkout_tests.csv', 'r') as f:
    csv_data = list(csv.DictReader(f))
    print(f"CSV: {len(csv_data)} records loaded")

# Read JSON
with open('saucedemo_checkout_tests.json', 'r') as f:
    json_data = json.load(f)
    print(f"JSON: {json_data['metadata']['total_tests']} records loaded")
    print(f"Generated at: {json_data['metadata']['generated_at']}")

print("\n✅ Both files verified successfully!")
```

---

### Deliverable Format

Save as `mentee-work/week-11/test-data-randomizer.md`

```markdown
# Week 11 - Exercise 5: Complete Test Data Script

**Your Name:** [Your name]
**Date:** [Date]

---

## Script Output

```
[Paste full output of test_data_master.py]
```

---

## Generated Files

### CSV Sample (First 10 rows)

```csv
[Paste first 10 rows from CSV file]
```

### JSON Metadata

```json
[Paste metadata section from JSON file]
```

---

## Verification

```
[Paste output of verify_data.py]
```

---

## Production-Ready Features

**What makes this script production-ready?**
1. [Your answer - e.g., "Generates both CSV and JSON formats"]
2. [Your answer]
3. [Your answer]

**How would you improve this script further?**
[Your ideas]

---

## Real-World Usage

**Scenario:** You need to test SauceDemo checkout 100 times with different data.

**Without this script:**
[Describe manual process - time, effort, errors]

**With this script:**
[Describe automated process - speed, accuracy, reusability]

**Time saved:** [Calculate hours saved]

---

## Portfolio Piece

**Could you show this in a FAANG interview?**
[Yes/No and why]

**What would you explain to an interviewer?**
[Your pitch - what problem it solves, how it works, what you learned]
```

---

### Success Criteria

- ✅ Script generates 50 random + 10 edge case records
- ✅ Saves to both CSV and JSON
- ✅ JSON includes metadata (timestamp, counts, etc.)
- ✅ Summary report displays statistics
- ✅ Files can be read and verified
- ✅ Production-ready quality (clean code, comments, error handling)

---

## 📂 Week 11 Submission Checklist

Before submitting, ensure you have:

### Deliverables
- [ ] `mentee-work/week-11/python-setup.md` - Setup verification
- [ ] `mentee-work/week-11/test-data-generator.md` - Exercise 2
- [ ] `mentee-work/week-11/csv-json-handling.md` - Exercise 3
- [ ] `mentee-work/week-11/simple-api-testing.md` - Exercise 4
- [ ] `mentee-work/week-11/test-data-randomizer.md` - Exercise 5
- [ ] All Python scripts (`.py` files) committed
- [ ] Generated test data files (CSV, JSON) committed
- [ ] All work committed to GitHub with clear commit messages
- [ ] Pull Request created with Week 11 submission template

### Quality Gates
- [ ] All Python scripts run without errors
- [ ] Test data files generated successfully
- [ ] API tests pass (all assertions succeed)
- [ ] Code follows Python naming conventions
- [ ] Comments explain what code does
- [ ] Reflection questions answered

### Portfolio Quality
- [ ] At least 1 script is "portfolio-worthy" (could show in interview)
- [ ] Demonstrates understanding of when automation adds value
- [ ] Shows practical QA problem-solving

---

## 🎯 Learning Outcomes

By completing these exercises, you should be able to:

- ✅ Set up Python development environment
- ✅ Write basic Python scripts (variables, loops, functions)
- ✅ Generate test data using Faker library
- ✅ Save/load data from CSV files
- ✅ Save/load data from JSON files
- ✅ Perform GET and POST API requests
- ✅ Validate API responses (status code, JSON structure)
- ✅ Explain when to use automation vs manual testing
- ✅ Build production-ready test data generation scripts

---

## 💡 Tips for Success

**Exercise 1 (Setup):**
- Check "Add to PATH" during Python installation (critical!)
- Verify installation BEFORE proceeding to exercises
- If stuck, try uninstall → reinstall Python

**Exercise 2 (Test Data):**
- Run examples in tutorial first to understand Faker
- Test with small numbers first (5 records) before generating 50
- Add print statements to debug if something doesn't work

**Exercise 3 (CSV/JSON):**
- CSV for humans (Excel), JSON for machines (APIs, code)
- Always close files (use `with open()` pattern)
- Check file exists before trying to read it

**Exercise 4 (API Testing):**
- Print response.status_code if test fails
- Print response.json() to see actual structure
- Use online JSON formatter if response is hard to read

**Exercise 5 (Complete Script):**
- Break it down: generate → save → verify
- Test each part separately before combining
- This is portfolio-quality - make it clean!

**General Python Tips:**
- Read error messages carefully (they tell you what's wrong!)
- Google error messages (you're not the first to see them)
- Use print() everywhere to debug
- Save often, run often

---

**Remember:** Week 11 is about practical QA automation, not becoming a Python expert. Focus on solving real QA problems (test data, API testing) with just enough Python. 🚀
