# this is still a DRAFT!!


## Requirements

- an `Employee`
- a `Payable account` for Salaries (like i.e. _Salaries Payable_)
- an `Expense account` for Salaries (lilke i.e. _Admin Salaries_)
`
## Accounting Transactions

It takes 2 `Journal Entries` for this to work. 
- One creates the Liability (a salary that needs to be paid) and 
- a second one equals that liability with a concrete money transfer (from the company to the employee) 

#### 1. creating the liability

A `Journal Entry` with two rows

- __row 1__ Salaries Payable: Credit (Party: Employee #1)
- __row 2__ Expense account:  Debit

posting date is the date when the salary is due.

#### 2. balancing the
with an actual money transfer (Company > Employee #1)

A `Journal Entry` with two rows

- __row 1__ Salaries Payable: Debit (Party: Employee #1)
- __row 2__ Company Bank Account:  Credit

posting date is the date of the actual bank transfer (most likey on or after the posting date of `Journal Entry`  1
