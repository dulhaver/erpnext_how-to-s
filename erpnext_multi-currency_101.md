### transactions/Doctypes that are not multi-currency ready yet in ERPNext

- Expense Claim
- Liability transactions where a `Party` is an **Employee** (like Jounral Entry to a Payable account with Party=Enployee)
- Payroll/Salary Slip
- PE "charges and fees"
- Membership (Non Profit Domain)
- Loan
- Opening Invoice Creation Tool
- return payments with Journel Entry
- (to be continued)

---

#### Expense Claim

#### Employee Advance
- can only be made in default currency


#### Salary Slip
- can only be set in default company currency
- agreements with staff in other currency cannot be correctly recorded.
- Calculations of base pay resulting from the agreed non-default currency is not automaticlaly recorded on monthly basis.
- e.g. StaffA contract is in USD as the staff is originally from USA, and company currency is in EUR as the company is in Europe. THe salary slip is only in EUR, and the calculations for taxes is based on EUR, and every month the base salary (salary slip allocation) is redone just because there is no place where the amount and currency of contract is stored to allow dynamic calculation of base salary from USD to EUR using the current exchange.


#### Payment Entry

`Deduction/Loss` does **not** accept non-default currency account, even if the entire transaction happens in (the same) non-default currency

#### Membership 
- The membership doctype is not having currency and so memberships can only be provided in single currency.

#### Loan
- The Loan doctype is also not having currency and so loans can only be disbursed and recovered in single currency. It also means that loan recovery amount changes every month from salary slip.


#### Opening Invoice Creation Tool
- only allows transactions in the default currency. If any of your customers or suppliers uses another currency, u can not use that tool to create an opening balance

#### Return payments with Journal Entry
if you have an Invoice with an attached Payment Entry and the payment is being returned you can make the Invoice unpaid with a Journal Entry and then balace it anew with a second payment entry. However when any of the components (Invoice, Payment) is in any non-default currency the second payment requires an Difference Ammount which is out of any proportion  https://discuss.erpnext.com/t/how-to-account-for-returned-payment-to-a-supplier/52891/6?u=vrms
