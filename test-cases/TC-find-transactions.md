# Test Cases: Find Transactions

**Preconditions for all cases below:** User is logged in and has an account with existing transaction history (deposits, transfers, bill payments).

---

## TC-TRANS-001 — Verify search by exact transaction amount returns correct result
**Priority:** High
**Test Data:** A known transaction amount, e.g. $100.00

**Steps:**
1. Navigate to "Find Transactions"
2. Select an **existing** account
3. Enter the known amount in "Find by Amount" search field
4. Click "Find Transaction"

**Expected Result:** The transaction(s) matching that exact amount are displayed, with correct date, description, and amount.

**Test Evidence:** 
<img width="912" height="647" alt="image" src="https://github.com/user-attachments/assets/8bac80d7-5453-45a1-b5c2-377eac54acce" />

**Status:** Pass

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

**Test Evidence:** 
<img width="933" height="903" alt="image" src="https://github.com/user-attachments/assets/f93cf7d5-93e0-47a5-a419-1320f29f847e" />
<img width="878" height="651" alt="image" src="https://github.com/user-attachments/assets/7afcaf1f-2202-43b9-9816-f988cdb4f97f" />

**Status:** Pass

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

**Test Evidence:** 
<img width="997" height="914" alt="image" src="https://github.com/user-attachments/assets/321830c4-f5bf-4991-9adb-cfe68812f4da" />
<img width="900" height="645" alt="image" src="https://github.com/user-attachments/assets/3fadb00a-dc60-4ebd-b0be-7ef43e77c587" />

**Status:** Pass

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

**Test Evidence:** 

<img width="888" height="903" alt="image" src="https://github.com/user-attachments/assets/bd9e36b2-d788-4ae2-9b95-596fd94d5051" />
<img width="881" height="643" alt="image" src="https://github.com/user-attachments/assets/2ea4e640-db8d-43e1-a124-241d5cd9ebb5" />

**Status:** Pass

---

## TC-TRANS-005 — Verify search with no matching results, incorrect format, incorrect value type shows an appropriate message
**Priority:** Medium
**Test Data:** An amount or date known to have no matching transactions (e.g. 99999.99/acb123/cba321/abc12345)

**Steps:**
1. Navigate to all filters
2. Search using criteria with no matches 
3. Click Find <field>

**Expected Result:** A clear "No transactions found/Incorrect <field>" message is displayed rather than an error or blank/broken page.

**Test Evidence:**
<img width="879" height="917" alt="image" src="https://github.com/user-attachments/assets/6bb8fb8b-cfa1-432c-87d6-1ce9a92c2c53" />

**Status:** Pass

---

## TC-TRANS-008 — Verify date range with "From" date after "To" date is handled correctly
**Priority:** Medium
**Test Data:** From: 07/20/2026, To: 07/01/2026 (invalid range, From > To)

**Steps:**
1. Navigate to "Find Transactions"
2. Enter a "From" date later than the "To" date
3. Click search

**Expected Result:** System shows a validation message about the invalid range, or returns zero results without error — should not crash or show incorrect data.

**Test Evidence:**
<img width="931" height="899" alt="image" src="https://github.com/user-attachments/assets/7fefa87e-fe5d-4f18-acba-a6867d4ebb02" />
<img width="913" height="655" alt="image" src="https://github.com/user-attachments/assets/b11f4664-16c9-4e5b-8340-b6f65223b6b2" />

**Status:** Pass with condition - Error message: "An internal error has occurred and has been logged".
