```sql
-- Convert from MRM to XML Format
SET OutputRoot.MRM.Data.Account = InputRoot.XMLNS.Data.Account;
```

```sql
-- Multiple Output Messages
SET OutputRoot = InputRoot; 
PROPAGATE DELETE NONE; 
SET OutputRoot = InputRoot; PROPAGATE TO TERMINAL 'out1' 
DELETE NONE; 
SET OutputRoot = InputRoot; PROPAGATE TO LABEL 'ThirdCopy';
```

```sql
-- Adding an interval to a datetime value
DECLARE retAge CHARACTER '65'; 
DECLARE birthDate DATE DATE '1953-06-01'; 
SET OutputRoot.XML.Test.retirementDate = birthDate + CAST(retAge AS INTERVAL YEAR);
```

```sql
-- Copying repeating Fields using Cardinality
SET I = 1; 
SET J = CARDINALITY(InputRoot.XMLNS.Field_top.field1[]); 
WHILE I <= J DO 
SET OutputRoot.XMLNS.Output_top.Outfield1[I] = InputRoot.XMLNS.Field_top.field1[I]; 
SET I = I + 1; 
END WHILE;
```

```sql
-- Accessing the MQMD Header
SET OutputRoot.MRM.Identifier = InputRoot.MQMD.MsgId;
```

```sql
-- Casting
DECLARE I INTEGER 1; 
DECLARE C CHARACTER;
SET C = CAST(I AS CHARACTER);
```