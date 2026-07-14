# Test Plan: Parabank - Login & Authentication

## 1. Objective
Verify that the login functionality works correctly for valid users, and fails safely and clearly for invalid input.

## 2. Scope
**In scope:**
- Login form (email/username + password)
- Error handling for invalid credentials
- Empty field validation

**Out of scope:**
- Password reset flow
- Social login (Google/Facebook)

## 3. Test Approach
- Manual functional testing
- Positive, negative, and edge-case scenarios
- Cross-browser check on Chrome and Firefox

## 4. Risk Areas
- Security: does the app reveal whether an email exists vs. password is wrong? (info leak risk)
- Usability: are error messages clear enough for users to self-correct?

## 5. Test Environment
- Browser: Chrome 126, Firefox 127
- OS: Windows 11
- URL: [[app URL]](https://parabank.parasoft.com/parabank/login.htm)

## 6. Deliverables
- Test cases (see `/test-cases/login.md`)
- Bug reports for any failures (see `/bug-reports/`)
- Summary of results (below, filled in after execution)

## 7. Summary of Results
- Total test cases: 4
- Passed: 4
- Failed: 0
- Bugs filed: 0
