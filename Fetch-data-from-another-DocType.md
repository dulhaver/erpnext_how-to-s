### Fetch data from a (Custom) field of another Doctype


> in this example we are going to fetch data from Custom Field "Supplier Code" 
from the **Customer** DocType into the **Purchase Order**

In **Purchase Order** Form create a custom field named "Supplier Code"
- field type is "data"
- in "Fetch From" say: `supplier.supplier_code` (DocType.field_name)
