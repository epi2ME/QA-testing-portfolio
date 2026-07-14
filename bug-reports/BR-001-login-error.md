# BR-001: Incorrect password shows generic 500 error instead of clear message

**Related Test Case:** TC-LOGIN-002

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

## Expected Result
A clear, user-facing error message: "Incorrect email or password."

## Actual Result
The page displays a generic "500 Internal Server Error" and the user is left with no explanation of what went wrong.

## Evidence
<img width="853" height="593" alt="image" src="https://github.com/user-attachments/assets/2d4b6698-d642-4f84-860b-19b18e182596" />

## Impact
Users who mistype their password get no guidance to correct it, likely increasing support requests and abandonment at login.

## Notes
Confirmed reproducible 3/3 attempts. Did not occur when password field was left empty (see TC-LOGIN-003, which passed).
