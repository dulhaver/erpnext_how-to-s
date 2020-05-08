### Issues with multi-currency transactions in ERPNext

> All this is detected in a version-11 instance I am running. I believe much (if not all) still is existant in v12/v13


#### Expense Claim / Employee Advance
- can only be made in default currency

#### Salary Slip
- can only be set in default company currency
- agreements with staff in other currency cannot be correctly recorded.
- Calculations of base pay resulting from the agreed non-default currency is not automaticlaly recorded on monthly basis.
- e.g. Staff contract is in USD as the staff is originally from USA, and company currency is in EUR as the company is in Europe. The salary slip is only in EUR, and the calculations for taxes is based on EUR, and every month the base salary (salary slip allocation) is redone just because there is no place where the amount and currency of contract is stored to allow dynamic calculation of base salary from USD to EUR using the current exchange.

#### Payment Entry
- `Deduction/Loss` does **not** accept non-default currency account, even if the entire transaction happens in (the same) non-default currency

#### Exchange Rate
- `Payment Entry`, `Journal Entry`, `Sales/Purchase Invoice/Order` grab the `exchange rate` from the date the transaction is entered into ERPNext, **not the transaction date**. This creates wrong "Difference Amount" value. https://github.com/frappe/erpnext/issues/21473.  
For Purchase Invoices the rate should be grabbed 1st from the `Supplier Invoice Date` and (if that was empty) from the `posting_date` I'd say.

There has been agreement in the "Accounts Working Group@ on Telegram this is regarded a bug, not a missing feature

#### Membership 
- The membership doctype is not having currency and so memberships can only be provided in single currency.

#### Loan
- The Loan doctype is also not having currency and so loans can only be disbursed and recovered in single currency. It also means that loan recovery amount changes every month from salary slip.


#### Opening Invoice Creation Tool
- only allows transactions in the default currency. If any of your customers or suppliers uses another currency, u can not use that tool to create an opening balance

#### Return payments with Journal Entry
if you have an Invoice with an attached Payment Entry and the payment is being returned (due to some error with the bank transaction i.e.) you can make the Invoice unpaid with a Journal Entry and then balance it anew with a second payment entry. However when any of the components (Invoice, Payment) is in any non-default currency the second payment requires a Difference Ammount which is out of any proportion  https://discuss.erpnext.com/t/how-to-account-for-returned-payment-to-a-supplier/52891/6?u=vrms
