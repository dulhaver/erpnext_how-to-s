# Requirements

- an `Employee`
- a `Payable account` for Salaries (i.e. _Salaries Payable_)
- an `Expense account` for Salaries (i.e. _Admin Salaries_)

# Accounting Transactions

It takes 2 `Journal Entries` for this to work. 
- One creates the Liability (a salary that needs to be paid) and 
- a second one equals that liability with a concrete money transfer (from the company to the employee) 

## **1. creating the liability**

A `Journal Entry` with two rows

- row 1 __Salaries Payable: Credit__ (Party: Employee #1)
- row 2 __Expense account:  Debit__

posting date is the date when the salary is due.

**Attention here!**: In order to be able to select the Employee as PArty Type you need to open the details of the entry. By default the Party Type it is set to be `Supplier`

## **2. balancing the liabilty**
with an actual money transfer (Company > Employee #1)

A `Journal Entry` with two rows

- row 1 __Salaries Payable: Debit__ (Party: Employee #1)
- row 2 __Company Bank Account:  Credit__

posting date is the date of the actual bank transfer (most likey on or after the posting date of `Journal Entry`  1

----

tested on v11 on 2018-02-01
