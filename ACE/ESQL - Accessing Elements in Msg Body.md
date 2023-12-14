``` sql
-- Sets output same as input
SET OutputRoot.XMLNS.Invoice.Customer.FirstName = InputBody.Invoice.Customer.FirstName;
```

```sql
-- Writes all records from the input Invoice message to the output message
-- Declare local variable 
DECLARE CurrentCustomer CHAR 'Smith'; -- Loop through the input message 
SET OutputRoot.XMLNS.Invoice[] = 
(SELECT I FROM InputRoot.XMLNS.Invoice[] AS I 
 WHERE I.Customer.LastName = CurrentCustomer );
```

```sql
-- Field[<2] indicates the last but one element
-- Field[<] indicates the last element
IF Body.Invoice.Customer.Billing.Address[<] = 'Hampshire' THEN DO; 
--more ESQL 
END IF; 
IF Body.Invoice.Customer.Billing.Address[<2 ] = 'Southampton' THEN DO; 
-- more ESQL 
END IF;
```

```sql
FOR ANY Body.Invoice.Purchases."Item"[]
AS I (I.Book IS NOT NULL AND I.Book.Title = 'C Primer')
```

```sql
-- Declare the dynamic reference 
DECLARE myref REFERENCE TO OutputRoot.XMLNS.Invoice.Purchases.Item[1]; 
-- Continue processing for each item in the array 
WHILE LASTMOVE(myref)=TRUE DO -- Add 1 to each item in the array 
SET myref = myref + 1; 
-- Move the dynamic reference to the next item in the array 
MOVE myref NEXTSIBLING; 
END WHILE;
```

