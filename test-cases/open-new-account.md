# Test Cases: Open New Account

**Preconditions for all cases below:** User is registered and logged in; has at least one existing account (e.g. Checking) with a balance.

---

## TC-ACCT-001 — Verify user can open a new Savings account
**Priority:** High

**Steps:**
1. Log in with valid credentials
2. Navigate to "Open New Account"
3. Select account type: "Savings"
4. Select an existing account to transfer initial funds from
5. Click "Open New Account"

**Expected Result:** Confirmation page displays with a new account number. New account appears under "Accounts Overview."

**Status:** Not Executed

---

## TC-ACCT-002 — Verify user can open a new Checking account
**Priority:** High

**Steps:**
1. Log in with valid credentials
2. Navigate to "Open New Account"
3. Select account type: "Checking"
4. Select an existing account to fund it from
5. Click "Open New Account"

**Expected Result:** New Checking account is created and listed in Accounts Overview with correct type.

**Status:** Not Executed

---

## TC-ACCT-003 — Verify minimum balance requirement is enforced (if applicable)
**Priority:** Medium

**Test Data:** Funding account with balance below the minimum required (e.g. $0 or $50 if a $100 minimum applies)

**Steps:**
1. Log in with valid credentials
2. Navigate to "Open New Account"
3. Select account type: "Savings"
4. Choose a funding account with insufficient balance
5. Click "Open New Account"

**Expected Result:** System either blocks account creation with a clear error message, or clearly states no minimum balance is required. Behavior should be consistent with stated business rules.

**Status:** Not Executed

---

## TC-ACCT-004 — Verify new account number is unique
**Priority:** Medium

**Steps:**
1. Open two new accounts in succession (repeat TC-ACCT-001 twice)
2. Compare the account numbers generated

**Expected Result:** Each new account is assigned a distinct, unique account number.

**Status:** Not Executed

---

## TC-ACCT-005 — Verify newly opened account reflects correct starting balance
**Priority:** High

**Test Data:** Transfer amount: $100 from Checking to new Savings account

**Steps:**
1. Note the funding account's balance before opening the new account
2. Open a new Savings account, transferring $100 from Checking
3. Go to Accounts Overview after confirmation

**Expected Result:** New Savings account shows a starting balance of $100. Funding (Checking) account balance is reduced by $100.

**Status:** Not Executed

---

## TC-ACCT-006 — Verify behavior when no funding account is available
**Priority:** Low

**Preconditions:** Test with a user who has no existing accounts (edge case, may not be reachable via UI)

**Expected Result:** System should not allow account creation without a valid "transfer from" account, or should clearly explain the requirement.

**Status:** Not Executed / Blocked

---

## TC-ACCT-007 — Verify UI validation when required fields are not selected
**Priority:** Medium

**Steps:**
1. Navigate to "Open New Account"
2. Leave "Account Type" or "Transfer From" unselected (if possible)
3. Click "Open New Account"

**Expected Result:** Form prevents submission or shows a validation message; no account is created.

**Status:** Not Executed
