# Test Cases: Transfer Funds

**Preconditions for all cases below:** User is logged in and has at least two accounts (e.g. Checking with $500, Savings with $200).

---

## TC-XFER-001 — Verify successful transfer between two valid accounts
**Priority:** High
**Test Data:** From: Checking ($500), To: Savings ($200), Amount: $100

**Steps:**
1. Navigate to "Transfer Funds"
2. Select "From" account: Checking
3. Select "To" account: Savings
4. Enter amount: $100
5. Click "Transfer"

**Expected Result:** Confirmation message shown ("$100.00 has been transferred..."). Checking balance reduces to $400, Savings balance increases to $300.

**Status:** Not Executed

---

## TC-XFER-002 — Verify transfer fails when amount exceeds available balance
**Priority:** High
**Test Data:** From: Savings ($200), To: Checking, Amount: $5000

**Steps:**
1. Navigate to "Transfer Funds"
2. Select From: Savings, To: Checking
3. Enter amount: $5000
4. Click "Transfer"

**Expected Result:** Transfer is rejected with a clear error message (e.g. "insufficient funds"). No balance changes on either account.

**Status:** Not Executed

---

## TC-XFER-003 — Verify transfer fails with zero amount
**Priority:** Medium
**Test Data:** Amount: $0

**Steps:**
1. Navigate to "Transfer Funds"
2. Select valid From/To accounts
3. Enter amount: 0
4. Click "Transfer"

**Expected Result:** System rejects the transfer with a validation message; no funds move.

**Status:** Not Executed

---

## TC-XFER-004 — Verify transfer fails with negative amount
**Priority:** High
**Test Data:** Amount: -50

**Steps:**
1. Navigate to "Transfer Funds"
2. Select valid From/To accounts
3. Enter amount: -50
4. Click "Transfer"

**Expected Result:** System rejects negative input, either via inline validation or a clear error message. No funds move.

**Status:** Not Executed

---

## TC-XFER-005 — Verify transfer fails with non-numeric amount
**Priority:** Medium
**Test Data:** Amount: "abc"

**Steps:**
1. Navigate to "Transfer Funds"
2. Select valid From/To accounts
3. Enter amount: "abc"
4. Click "Transfer"

**Expected Result:** Field rejects non-numeric input or form shows a validation error; no transfer is processed.

**Status:** Not Executed

---

## TC-XFER-006 — Verify user cannot transfer to the same account (From = To)
**Priority:** Medium
**Test Data:** From: Checking, To: Checking, Amount: $50

**Steps:**
1. Navigate to "Transfer Funds"
2. Select the same account for both "From" and "To"
3. Enter a valid amount
4. Click "Transfer"

**Expected Result:** System either blocks this with a clear message, or processes it with balance unchanged (define expected business rule and note actual behavior).

**Status:** Not Executed

---

## TC-XFER-007 — Verify transfer with decimal amount is handled correctly
**Priority:** Medium
**Test Data:** Amount: $25.75

**Steps:**
1. Navigate to "Transfer Funds"
2. Select valid From/To accounts
3. Enter amount: 25.75
4. Click "Transfer"

**Expected Result:** Transfer succeeds; both account balances reflect the exact decimal amount.

**Status:** Not Executed

---

## TC-XFER-008 — Verify transferred amount appears in transaction history
**Priority:** High

**Steps:**
1. Complete a successful transfer (e.g. TC-XFER-001)
2. Navigate to "Accounts Overview" → select the "From" account → view transactions
3. Navigate to the "To" account → view transactions

**Expected Result:** A debit transaction appears on the "From" account and a credit transaction appears on the "To" account, both matching the transferred amount and timestamp.

**Status:** Not Executed
