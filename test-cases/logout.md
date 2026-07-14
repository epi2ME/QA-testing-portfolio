# Test Cases: Logout

**Preconditions for all cases below:** User is logged in with a valid session.

---

## TC-LOGOUT-001 — Verify user can log out successfully
**Priority:** High

**Steps:**
1. While logged in, click the "Log Out" link
2. Observe the resulting page

**Expected Result:** User is redirected to the login/landing page. A logged-out state is clearly indicated (e.g. Customer Login form is shown again).

**Test Evidence:**

<img width="855" height="645" alt="image" src="https://github.com/user-attachments/assets/a23f5ce9-3490-472d-8e70-cf87d7f0a66a" />
<img width="924" height="772" alt="image" src="https://github.com/user-attachments/assets/5f7ad084-c93f-470e-82cb-92975ae49ec8" />

**Status:** Pass

---

## TC-LOGOUT-002 — Verify session is invalidated after logout (back button test)
**Priority:** High

**Steps:**
1. Log in and navigate to "Accounts Overview"
2. Click "Log Out"
3. Click the browser's Back button

**Expected Result:** User should not see cached account data without re-authenticating; ideally redirected to login if attempting further navigation, or a message indicating the session has ended.

**Test Evidence:**

<img width="899" height="650" alt="image" src="https://github.com/user-attachments/assets/0b3de66b-28c8-448b-a7dc-525e96847013" />

**Status:** Fail  See BR-001-logout-error.md

---

## TC-LOGOUT-003 — Verify protected pages are inaccessible after logout via direct URL
**Priority:** High

**Steps:**
1. Log in and copy the URL of "Accounts Overview" (or another account page)
2. Click "Log Out"
3. Paste and navigate directly to the copied URL

**Expected Result:** User is redirected to the login page rather than being shown account data.

**Test Evidence:**

<img width="822" height="598" alt="image" src="https://github.com/user-attachments/assets/c751952e-0cbb-4c58-91e6-3bd8bda869bd" />

**Status:** Pass

---

## TC-LOGOUT-004 — Verify "Log Out" is available from all major pages when logged in
**Priority:** Low

**Steps:**
1. Log in
2. Navigate to several pages (Accounts Overview, Transfer Funds, Bill Pay, etc.)
3. Confirm "Log Out" link/button is visible and accessible on each

**Expected Result:** Logout option is consistently available across the logged-in experience.

**Test Evidence:**

<img width="822" height="598" alt="image" src="https://github.com/user-attachments/assets/c751952e-0cbb-4c58-91e6-3bd8bda869bd" />

**Status:** Pass

---

## TC-LOGOUT-005 — Verify logging back in after logout works correctly
**Priority:** Medium

**Steps:**
1. Log in, then log out
2. Log in again with the same valid credentials

**Expected Result:** User can log back in successfully and sees correct, up-to-date account data (no stale session data from before).

**Test Evidence:**

<img width="893" height="669" alt="image" src="https://github.com/user-attachments/assets/f175d968-5d18-46de-9f94-c81ee320f5fd" />

**Status:** Pass
