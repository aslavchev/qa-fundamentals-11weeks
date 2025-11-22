# Week 4 – Security Checklist 

## 1. Authentication
- [ ] Password is hidden
- [ ] Invalid login shows error message
- [ ] Empty username/password is not allowed
- [ ] Logout redirects to login page
- [ ] Cannot access inventory page after logout

## 2. Session Management
- [ ] Session cookie appears after login
- [ ] Cookie is removed after logout
- [ ] Cannot open `/inventory.html` without logging in

## 3. Input Validation (Checkout)
- [ ] Required fields block empty input (First Name, Last Name, Postal Code)
- [ ] Error message appears for missing field
- [ ] Entering special characters does not break the page
- [ ] Script tags (`<script>`) do not execute

## 4. URL Protection
- [ ] Cannot access checkout steps directly without items in cart
- [ ] Cannot skip to step two before step one
- [ ] Direct URL access without login redirects to login page

## 5. HTTPS / Basic Security
- [ ] Site uses HTTPS
- [ ] No mixed content warnings
- [ ] No sensitive data visible in URL or page source

## Notes
- In the site there is an issue concerning the Checkout Information page, where the user can enter First name/Last name/Zip code with inappropriate format.
