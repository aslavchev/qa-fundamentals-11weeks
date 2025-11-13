# SauceDemo – System Test Scenarios

## System Test Scenario #1

**Test ID:** SYS-1  
**Test Title:** Happy Path - Complete Purchase  
**Test Type:** End-to-End / Workflow / Functional  

**User Story:**  
As a standard user, I want to complete a purchase from login to order confirmation, so that I can successfully buy products.  

**Preconditions:**  
- Application is accessible  
- Test data is prepared  

**Test Steps:**  
1. Navigate to login page  
2. Enter Username: `standard_user` and Password: `secret_sauce`  
3. Click “Login”  
4. Browse products and select one  
5. Click “Add to Cart”  
6. Open Cart and click “Checkout”  
7. Fill in checkout form (First Name, Last Name, Postal Code)  
8. Click “Continue” → review overview  
9. Click “Finish” → order confirmation page  

**Expected Results:**  
- Product appears in cart  
- Checkout steps complete successfully  
- Confirmation page displays correct order details  

**Test Data:**  
- Username: standard_user  
- Password: secret_sauce  
- Product: Sauce Labs Backpack  

**Verification Points:**  
- [ ] Login successful  
- [ ] Cart updated correctly  
- [ ] Checkout completed with order confirmation  

---

## System Test Scenario #2

**Test ID:** SYS-2  
**Test Title:** Product Browsing and Sorting  
**Test Type:** End-to-End / Workflow / Functional  

**User Story:**  
As a standard user, I want to sort products by different criteria, so that I can easily find items.  

**Preconditions:**  
- Logged in as standard_user  
- Product catalog loaded  

**Test Steps:**  
1. Navigate to product catalog  
2. Use sort dropdown: Name (A-Z) → verify order  
3. Sort by Name (Z-A) → verify order  
4. Sort by Price (Low → High) → verify order  
5. Sort by Price (High → Low) → verify order  

**Expected Results:**  
- Products reorder correctly according to selection  
- No products missing or duplicated  

**Test Data:**  
- Username: standard_user  
- Password: secret_sauce  

**Verification Points:**  
- [ ] Sorting by name works  
- [ ] Sorting by price works  
- [ ] Product display consistent  

---

## System Test Scenario #3

**Test ID:** SYS-3  
**Test Title:** Cart Management  
**Test Type:** End-to-End / Workflow / Functional  

**User Story:**  
As a standard user, I want to manage my cart (add, remove, update quantities), so that my order is correct.  

**Preconditions:**  
- Logged in  
- Product catalog loaded  

**Test Steps:**  
1. Add multiple items to cart  
2. Navigate to cart  
3. Update quantity of an item  
4. Remove an item from cart  
5. Verify total price updates  

**Expected Results:**  
- Cart reflects all changes correctly  
- Total price updates accordingly  

**Test Data:**  
- Products: Backpack, Bike Light, Bolt T-Shirt  

**Verification Points:**  
- [ ] Items added correctly  
- [ ] Quantity update reflected  
- [ ] Item removal reflected  

---

## System Test Scenario #4

**Test ID:** SYS-4  
**Test Title:** Checkout Form Validation  
**Test Type:** End-to-End / Workflow / Functional  

**User Story:**  
As a user, I want checkout form validation, so that I cannot submit incomplete or invalid data.  

**Preconditions:**  
- Logged in  
- At least one item in cart  

**Test Steps:**  
1. Go to checkout page  
2. Leave First Name blank → Click Continue → observe error  
3. Leave Last Name blank → Click Continue → observe error  
4. Leave Postal Code blank → Click Continue → observe error  
5. Fill in all fields correctly → Continue  

**Expected Results:**  
- Errors appear for missing fields  
- User cannot proceed until all fields are valid  
- Successful submission navigates to overview page  

**Test Data:**  
- Username: standard_user  
- Password: secret_sauce  

**Verification Points:**  
- [ ] Error messages display correctly  
- [ ] Successful submission allowed only with valid data  

---

## System Test Scenario #5

**Test ID:** SYS-5  
**Test Title:** Multi-item Purchase  
**Test Type:** End-to-End / Workflow / Functional  

**User Story:**  
As a user, I want to buy multiple products at once, so that I can complete one transaction for all items.  

**Preconditions:**  
- Logged in  
- Product catalog loaded  

**Test Steps:**  
1. Add 3 different products to cart  
2. Proceed to checkout  
3. Fill in form  
4. Review overview page  
5. Finish purchase  

**Expected Results:**  
- All 3 products appear in checkout overview  
- Totals match cart  
- Confirmation page shows all items  

**Test Data:**  
- Username: standard_user  
- Password: secret_sauce  
- Products: Backpack, Bike Light, Fleece Jacket  

**Verification Points:**  
- [ ] Cart and checkout totals match  
- [ ] All products confirmed  

---

## System Test Scenario #6

**Test ID:** SYS-6  
**Test Title:** Cancel and Resume Shopping  
**Test Type:** End-to-End / Workflow / Functional  

**User Story:**  
As a user, I want to cancel checkout and continue shopping, so that I can modify my order.  

**Preconditions:**  
- Logged in  
- Product in cart  

**Test Steps:**  
1. Add product to cart  
2. Start checkout process  
3. Click “Cancel”  
4. Return to catalog  
5. Add more products  

**Expected Results:**  
- User returns to catalog  
- Previously added products remain in cart  
- New products can be added  

**Test Data:**  
- Username: standard_user  
- Password: secret_sauce  

**Verification Points:**  
- [ ] Cart preserved after cancel  
- [ ] User can continue shopping  

---

## System Test Scenario #7

**Test ID:** SYS-7  
**Test Title:** Invalid Login Handling  
**Test Type:** End-to-End / Workflow / Functional  

**User Story:**  
As a user, I want to see proper error messages for invalid login, so that I know why login failed.  

**Preconditions:**  
- Application accessible  

**Test Steps:**  
1. Enter invalid username/password  
2. Click “Login”  
3. Observe error message  
4. Enter valid credentials → Login  

**Expected Results:**  
- Error displayed for invalid credentials  
- Successful login possible with correct credentials  

**Test Data:**  
- Invalid: wrong_user / wrong_pass  
- Valid: standard_user / secret_sauce  

**Verification Points:**  
- [ ] Error message correct  
- [ ] Login works after valid credentials  

---

## System Test Scenario #8

**Test ID:** SYS-8  
**Test Title:** Product Detail Navigation  
**Test Type:** End-to-End / Workflow / Functional  

**User Story:**  
As a user, I want to view product details before adding to cart, so that I can make informed decisions.  

**Preconditions:**  
- Logged in  
- Product catalog loaded  

**Test Steps:**  
1. Click on a product  
2. View product details (description, price, image)  
3. Add product to cart  
4. Verify item in cart  

**Expected Results:**  
- Product detail page displays correct information  
- Added product appears in cart  

**Test Data:**  
- Product: Sauce Labs Backpack  

**Verification Points:**  
- [ ] Details displayed accurately  
- [ ] Cart updated correctly  

---

## System Test Scenario #9

**Test ID:** SYS-9  
**Test Title:** Logout and Session Management  
**Test Type:** End-to-End / Workflow / Functional  

**User Story:**  
As a user, I want session to persist correctly and logout to clear session, so that my account is secure.  

**Preconditions:**  
- Logged in  
- Product in cart  

**Test Steps:**  
1. Add product to cart  
2. Logout  
3. Login again with same credentials  
4. Navigate to cart  

**Expected Results:**  
- Cart items persist if required by app logic  
- Logout clears session appropriately  
- User can continue shopping after login  

**Test Data:**  
- Username: standard_user  
- Password: secret_sauce  

**Verification Points:**  
- [ ] Session cleared on logout  
- [ ] Cart behavior correct after login  

---

## System Test Scenario #10

**Test ID:** SYS-10  
**Test Title:** Complete Flow with Different User Types  
**Test Type:** End-to-End / Workflow / Functional  

**User Story:**  
As different user types, I want to complete key workflows, so that the application handles various scenarios.  

**Preconditions:**  
- Application accessible  

**Test Steps:**  
1. Login as `standard_user` → complete a purchase  
2. Login as `problem_user` → attempt same workflow → observe issues  
3. Login as `performance_glitch_user` → complete workflow → observe performance  

**Expected Results:**  
- `standard_user` completes purchase successfully  
- `problem_user` shows known issues (as expected)  
- `performance_glitch_user` completes workflow with delays  

**Test Data:**  
- Usernames: standard_user, problem_user, performance_glitch_user  
- Password: secret_sauce  

**Verification Points:**  
- [ ] Standard workflow successful  
- [ ] Known issues observed for problem_user  
- [ ] Performance metrics acceptable for performance_glitch_user  
