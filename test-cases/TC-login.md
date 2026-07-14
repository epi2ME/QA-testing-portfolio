# Test Cases: Login

## TC-LOGIN-001 — Verify successful login with valid credentials
**Priority:** High

**Preconditions:** User account exists with valid credentials

**Test Evidence:** <img width="956" height="661" alt="image" src="https://github.com/user-attachments/assets/ceab0da1-08d3-4f9e-8a59-33ce563da102" />
**Test Data:** email: `epitome`, password: `12345`

**Steps:**
1. Navigate to the login page
2. Enter valid email
3. Enter valid password
4. Click "LOG IN"

**Expected Result:** User is redirected to the dashboard/home page and sees their account name/avatar.

**Status:** Pass

---

## TC-LOGIN-002 — Verify login fails with incorrect password
**Priority:** High
**Preconditions:** User account exists - user is on login page

**Test Evidence:** <img width="978" height="630" alt="image" src="https://github.com/user-attachments/assets/1089d583-70d1-494d-a23b-0c432d7eeca2" />
**Test Data:** email: `epitome`, password: `123456`


**Steps:**
1. Navigate to the login page
2. Enter valid email
3. Enter incorrect password
4. Click "LOG IN"

**Expected Result:** Error message "The username and password could not be verified." is shown. User is not logged in.

**Status:** Pass

---

## TC-LOGIN-003 — Verify login fails with empty fields
**Priority:** Medium
**Preconditions:** User is on login page

**Steps:**
1. Leave email and password fields blank
2. Click "Login"

**Expected Result:** Inline validation errors appear under each empty field; form does not submit.

**Test Evidence:** <img width="973" height="626" alt="image" src="https://github.com/user-attachments/assets/3e94655d-ecfb-427d-bc9e-89cd6cd9a4f9" />

**Status:** Pass

---

## TC-LOGIN-004 — Verify SQL injection attempt is safely rejected
**Priority:** High
**Preconditions:** User is on login page
**Test Data:** email: `' OR '1'='1`, password: `' OR '1'='1`

**Steps:**
1. Enter the test data above into email and password fields
2. Click "Login"

**Expected Result:** Login fails safely with a generic error message; no system error or unauthorized access occurs. The error should be 400 Bad Request or 422 Unprocessable Entity

**Test Evidence:** <img width="1040" height="144" alt="image" src="https://github.com/user-attachments/assets/742aafe8-906c-4545-b596-cb2239e53b53" />

**Status:** Pass
