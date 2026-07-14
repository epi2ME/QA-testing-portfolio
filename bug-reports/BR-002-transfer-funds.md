# BR-002: Transfer of < Balance Amount and Negative Balance Amount.

**Related Test Case:** TC-XFER-002

**Severity:** High

**Priority:** High

**Status:** Open

## Environment
- Browser: Chrome 126
- OS: Windows 11
- URL: https://parabank.parasoft.com/parabank/register.htm

**Test Data:** 
From: Checking ($200), To: Savings, Amount: $5000
From: Checking ($200), To: Savings, Amount: $-4000

**Test Steps:**

1. Navigate to "Transfer Funds"
2. Select From: Savings, To: Checking
3. Enter amount: $5000 or $-4000
4. Click "Transfer"

## Expected Result
Expected Result: Transfer is rejected with a clear error message (e.g. "insufficient funds"). No balance changes on either account.

## Actual Result
The transfer was accepted no matter the balance amount or transfer amount.

## Evidence
<img width="864" height="641" alt="image" src="https://github.com/user-attachments/assets/82f3d603-dca6-4a14-9474-3022f23d4549" />
<img width="868" height="655" alt="image" src="https://github.com/user-attachments/assets/a5c2dd36-4fe4-4730-9abc-f619d5fc8cf8" />
<img width="824" height="665" alt="image" src="https://github.com/user-attachments/assets/15d90ee6-9446-4c2d-a1e9-c493fc160169" />
<img width="859" height="676" alt="image" src="https://github.com/user-attachments/assets/6f1f4579-0802-489f-8b0a-a39860b5a352" />
<img width="840" height="665" alt="image" src="https://github.com/user-attachments/assets/e0277dd5-a018-4686-a8ce-bd73eade786c" />

## Impact
The business should be clear with the requirements if the balance is '0' or negative amount. The transfer will be blocked.
