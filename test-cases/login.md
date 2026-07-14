# Test Cases: Login

## TC-LOGIN-001 — Verify successful login with valid credentials
**Priority:** High
**Preconditions:** User account exists with valid credentials
**Test Data:** email: `testuser@example.com`, password: `ValidPass123`

**Steps:**
1. Navigate to the login page
2. Enter valid email
3. Enter valid password
4. Click "Login"

**Expected Result:** User is redirected to the dashboard/home page and sees their account name/avatar.

**Status:** Pass

---

## TC-LOGIN-002 — Verify login fails with incorrect password
**Priority:** High
**Preconditions:** User account exists; user is on login page
**Test Data:** email: `testuser@example.com`, password: `WrongPass123`

**Steps:**
1. Navigate to the login page
2. Enter valid email
3. Enter incorrect password
4. Click "Login"

**Expected Result:** Error message "Incorrect email or password" is shown. User is not logged in.

**Status:** Fail — see BR-001

---

## TC-LOGIN-003 — Verify login fails with empty fields
**Priority:** Medium
**Preconditions:** User is on login page

**Steps:**
1. Leave email and password fields blank
2. Click "Login"

**Expected Result:** Inline validation errors appear under each empty field; form does not submit.

**Status:** Pass

---

## TC-LOGIN-004 — Verify SQL injection attempt is safely rejected
**Priority:** High
**Preconditions:** User is on login page
**Test Data:** email: `' OR '1'='1`, password: `' OR '1'='1`

**Steps:**
1. Enter the test data above into email and password fields
2. Click "Login"

**Expected Result:** Login fails safely with a generic error message; no system error or unauthorized access occurs.

**Status:** Pass

---

*(Add more: password field masking, "remember me" checkbox, account lockout after N failed attempts, case-sensitivity of email, etc.)*
