# Test Cases: Find Transactions

**Preconditions for all cases below:** User is logged in and has an account with existing transaction history (deposits, transfers, bill payments).

---

## TC-TRANS-001 — Verify search by exact transaction amount returns correct result
**Priority:** High
**Test Data:** A known transaction amount, e.g. $100.00

**Steps:**
1. Navigate to "Find Transactions"
2. Select the account
3. Enter the known amount in "Amount" search field
4. Click search

**Expected Result:** The transaction(s) matching that exact amount are displayed, with correct date, description, and amount.

**Status:** Not Executed

---

## TC-TRANS-002 — Verify search by date returns correct result
**Priority:** High
**Test Data:** A known transaction date

**Steps:**
1. Navigate to "Find Transactions"
2. Select the account
3. Enter the known date
4. Click search

**Expected Result:** Transactions from that specific date are listed; no transactions from other dates appear.

**Status:** Not Executed

---

## TC-TRANS-003 — Verify search by date range returns correct results
**Priority:** High
**Test Data:** From date and To date spanning multiple known transactions

**Steps:**
1. Navigate to "Find Transactions"
2. Select the account
3. Enter a "From" and "To" date range
4. Click search

**Expected Result:** All transactions within the range are shown; transactions outside the range are excluded. Results are correctly sorted (typically by date).

**Status:** Not Executed

---

## TC-TRANS-004 — Verify search by transaction ID returns the correct single transaction
**Priority:** Medium
**Test Data:** A known valid transaction ID

**Steps:**
1. Navigate to "Find Transactions"
2. Select the account
3. Enter the transaction ID
4. Click search

**Expected Result:** Exactly one transaction is returned, matching the ID, with correct details.

**Status:** Not Executed

---

## TC-TRANS-005 — Verify search with no matching results shows an appropriate message
**Priority:** Medium
**Test Data:** An amount or date known to have no matching transactions (e.g. $99999.99)

**Steps:**
1. Navigate to "Find Transactions"
2. Search using criteria with no matches
3. Click search

**Expected Result:** A clear "no transactions found" message is displayed rather than an error or blank/broken page.

**Status:** Not Executed

---

## TC-TRANS-006 — Verify search with invalid transaction ID (non-numeric) is handled gracefully
**Priority:** Medium
**Test Data:** Transaction ID: "abc123"

**Steps:**
1. Navigate to "Find Transactions"
2. Enter a non-numeric value in the Transaction ID field
3. Click search

**Expected Result:** System shows a validation error or "not found" message; does not throw a server error.

**Status:** Not Executed

---

## TC-TRANS-007 — Verify search with empty/blank criteria is handled correctly
**Priority:** Low

**Steps:**
1. Navigate to "Find Transactions"
2. Leave all search fields blank
3. Click search

**Expected Result:** System either prompts the user to enter at least one search criterion, or returns all transactions — behavior should be consistent with what's documented/expected.

**Status:** Not Executed

---

## TC-TRANS-008 — Verify date range with "From" date after "To" date is handled correctly
**Priority:** Medium
**Test Data:** From: 07/20/2026, To: 07/01/2026 (invalid range, From > To)

**Steps:**
1. Navigate to "Find Transactions"
2. Enter a "From" date later than the "To" date
3. Click search

**Expected Result:** System shows a validation message about the invalid range, or returns zero results without error — should not crash or show incorrect data.

**Status:** Not Executed
