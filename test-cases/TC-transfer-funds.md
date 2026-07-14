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

**Test Evidence:**
<img width="813" height="643" alt="image" src="https://github.com/user-attachments/assets/ff9db3b4-5875-4d74-b760-2204793a55d5" />
<img width="864" height="638" alt="image" src="https://github.com/user-attachments/assets/fba20e81-47d1-4ab9-a36f-7bfbe8af70cf" />
<img width="826" height="640" alt="image" src="https://github.com/user-attachments/assets/19017fbc-679a-4c8f-b7d0-6d1f40637240" />


**Status:** Pass
**Notes:** There are no Activity Center module to see the transaction stated in the message.

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

**Test Evidence:**
<img width="846" height="648" alt="image" src="https://github.com/user-attachments/assets/f3b631e9-be36-4ad6-bcfe-da2df3a19c8a" />
<img width="818" height="645" alt="image" src="https://github.com/user-attachments/assets/5899e12a-ad50-4abf-8d9a-363ba720d32e" />

**Status:** Fail

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

**Test Evidence:**
<img width="848" height="649" alt="image" src="https://github.com/user-attachments/assets/f7729a6f-f5f2-4309-acfa-787ced48543f" />
<img width="835" height="650" alt="image" src="https://github.com/user-attachments/assets/d7e6507a-793c-4174-9c25-68fa054cc810" />
<img width="809" height="645" alt="image" src="https://github.com/user-attachments/assets/6b238d1f-a9ba-4ec1-b2da-1436a1bb723b" />

**Status:** Fail

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

**Test Evidence:**
<img width="822" height="645" alt="image" src="https://github.com/user-attachments/assets/5a91c937-503b-424e-80ab-a4b0b93a2441" />
<img width="837" height="646" alt="image" src="https://github.com/user-attachments/assets/b8fad0a2-837e-4ed3-a3b9-b4d9c1ec71a0" />
<img width="820" height="643" alt="image" src="https://github.com/user-attachments/assets/f18edee4-6255-44fd-95aa-04f3e6695454" />

**Status:** Fail

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

**Test Evidence:**
<img width="820" height="654" alt="image" src="https://github.com/user-attachments/assets/6996d080-0121-45d8-9f4c-4c04694eba3d" />
<img width="836" height="652" alt="image" src="https://github.com/user-attachments/assets/6f624731-fe85-45ec-b251-88882f151e0d" />

**Status:** Pass

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

**Test Evidence:**
<img width="836" height="642" alt="image" src="https://github.com/user-attachments/assets/94cccb87-7b48-4718-9e5d-d5d75e9550ee" />
<img width="806" height="632" alt="image" src="https://github.com/user-attachments/assets/b8bcfa96-ccbd-4697-b0b7-af9f44ffaef5" />

**Status:** Fail

---

## TC-XFER-007 — Verify transfer with decimal amount is handled correctly
**Priority:** Medium
**Test Data:** Amount: $25.75

**Steps:**
1. Navigate to "Transfer Funds"
2. Select valid From/To accounts
3. Enter amount: 100.25
4. Click "Transfer"

**Expected Result:** Transfer succeeds; both account balances reflect the exact decimal amount.

**Test Evidence:**
<img width="846" height="647" alt="image" src="https://github.com/user-attachments/assets/e16aed71-26e0-4571-9140-e56c436e460f" />
<img width="821" height="651" alt="image" src="https://github.com/user-attachments/assets/3f856f24-6e9a-43cc-9153-243370804a81" />

**Status:** Pass

---

## TC-XFER-008 — Verify transferred amount appears in transaction history
**Priority:** High

**Steps:**
1. Complete a successful transfer (e.g. TC-XFER-001)
2. Navigate to "Accounts Overview" → select the "From" account → Find Transactions
3. Navigate to the "To" account → view transactions

**Expected Result:** A debit transaction appears on the "From" account and a credit transaction appears on the "To" account, both matching the transferred amount and timestamp.

**Test Evidence:**
<img width="824" height="645" alt="image" src="https://github.com/user-attachments/assets/8f8d7fe6-62f7-4156-bd0c-8ebe674b0b63" />

**Status:** Pass
