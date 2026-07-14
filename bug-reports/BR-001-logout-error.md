# BR-001: Verify session is invalidated after logout (back button test)

**Related Test Case:** TC-LOGOUT-002

**Severity:** High

**Priority:** High

**Status:** Open

## Environment
- Browser: Chrome 126
- OS: Windows 11
- URL: https://parabank.parasoft.com/parabank/register.htm

## Steps to Reproduce
1. Navigate to the login page
2. Enter a valid registered email address
3. Enter an incorrect password
4. Click "Login"
5. Click "Logout"
6. Check if all major modules are visible after clicking the back button following the logout process.

## Expected Result
The webpage should be redirected to the login page immediately after clicking the back button.

## Actual Result
After logout, the webpage displays the previous page instead of the login page..

## Evidence
<img width="841" height="641" alt="image" src="https://github.com/user-attachments/assets/579e1a94-addd-47b6-a2e4-9ca3f24f1f79" />

## Impact
Users who logout can stay and view the major modules after logout.
