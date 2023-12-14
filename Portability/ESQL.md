# Accessing Elements in Msg Body
``` sql
-- Sets output same as input
SET OutputRoot.XMLNS.Invoice.Customer.FirstName = InputBody.Invoice.Customer.FirstName;
```

```sql
IF InputBody.Invoice.Payment.CardType='Visa' THEN DO;
--More ESQL
END IF;
```

```sql
-- Writes all records from the input Invoice message to the output message
-- Declare local variable 
DECLARE CurrentCustomer CHAR 'Smith'; -- Loop through the input message 
SET OutputRoot.XMLNS.Invoice[] = 
(SELECT I FROM InputRoot.XMLNS.Invoice[] AS I 
 WHERE I.Customer.LastName = CurrentCustomer );
```

