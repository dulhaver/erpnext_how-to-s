### transactions/Doctypes that are not multi-currency ready yet in ERPNext

- Expense Claim
- Liability transactions where a `Party` is an **Employee** (like Jounral Entry to a Payable account with Party=Enployee)
- Payroll/Salary Slip
- PE "charges and fees"
- tbc ...

---

#### Expense Claim


#### Salary Slip ??
(tbc)


#### Payment Entry

`Deduction/Loss` does **not** accept non-default currency account, even if the entire transaction happens in (the same) non-default currency
