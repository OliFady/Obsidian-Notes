- The local environment tree includes a subtree called variables. This subtree is always created, but is never populated by the message flow.

```sql
SET OutputLocalEnvironment.Variables.OutputLocation = 'MQ';
IF InputLocalEnvironment.Variables.OutputLocation = 'MQ' 
THEN 
SET OutputLocalEnvironment.Destination.MQ.DestinationData.queueManagerName = 'myQManagerName'; 
SET OutputLocalEnvironment.Destination.MQ.DestinationData.queueName = 'myQueueName'; END IF;
```

- Data in environment is propagated as part of the logical tree to subsequent nodes in the message flow. If you create a new output message in a Compute node, the environment tree is also copied from the input message to the new output message.

```sql
SET Environment.Variables = 
ROW('granary' AS bread, 'reisling' AS wine, 'stilton' AS cheese); 
SET Environment.Variables.Colors[] = 
LIST{'yellow', 'green', 'blue', 'red', 'black'}; 
SET Environment.Variables.Country[] = 
LIST{ROW('UK' AS name, 'pound' AS currency), 
ROW('USA' AS name, 'dollar' AS currency)};
```

```sql
-- Access the ExceptionList
DECLARE start REFERENCE TO ExceptionList.*[1]; 
-- Loop through the exception list children 
WHILE start.Number IS NOT NULL DO 
-- more ESQL 
-- Move start to the last child of the field to which it currently points 
 MOVE start LASTCHILD; 
-- Move start to the Sibling of the field to which it currently points 
MOVE start NEXTSIBLING
END WHILE;
```