as this is not possible by `Make Payment` routine from within a Puchase Invoice again the `Journal Entry` comes to rescue


```
line      | Account                             | Party                    |  Dr/Cr   |
---------------------------------------------------------------------------------------
line 1    |  Payable account of PINV            | Supplier (against PINV)  |  Debit   |   
line 2    |  Payable account employee expenses  | Employee                 |  Credit  |  
```

this markes the PINV as paid and creates a liability against the Employee which can be tracked via the `General Ledger`
