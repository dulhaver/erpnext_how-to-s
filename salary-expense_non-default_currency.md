### **Scenario**

An Employee 
- receives Salary in a different then your Company's default Currency, or
- claims expenses in a non-default currency
- reimbursement/salary payment happens in to claim (non-default) currecny 

### **Problem**

The default ERPNext (v11.1.xx) does not allow Documents like "Salary Slip" or "Expense Claim" or transactions 
like Journal Entry linked to a Party of Party Type "Employee" in non-default currency 

Due to this limitation you have to create those claims (which create a liabilty in the Accounts against the Employee) 
and balance them with a payment in your Company's default currency. 
In case these to events do not happen at the exact same moment (which probably is a pretty common situation) you'll 
face the issue that the currency exchange rate between your default-currency and the claimed currency may vary.

### **dirty fix**

2 Journal Entries

1. Creates the Claim/liabilty for either Salary or expense
2. records the payment and balances the claim

... to be continued
