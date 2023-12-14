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



