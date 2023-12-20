```sql
-- copy headers 
DECLARE i INTEGER 1; 
DECLARE numHeaders INTEGER CARDINALITY(InputRoot.*[]); 
WHILE i < numHeaders DO SET OutputRoot.*[i] = InputRoot.*[i]; SET i = i + 1; 
END WHILE; 
CREATE FIELD OutputRoot.XMLNS.TestCase.description TYPE NameValue VALUE 'This is my TestCase'; 
CREATE FIRSTCHILD OF OutputRoot.XMLNS.TestCase Domain('XMLNS') NAME 'Identifier' VALUE InputRoot.XMLNS.TestCase.Identifier; 
CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase Domain('XMLNS') NAME 'Sport' VALUE InputRoot.XMLNS.TestCase.Sport; 
CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase Domain('XMLNS') NAME 'Date' VALUE InputRoot.XMLNS.TestCase.Date; 
CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase Domain('XMLNS') NAME 'Type' VALUE InputRoot.XMLNS.TestCase.Type; 
CREATE FIELD OutputRoot.XMLNS.TestCase.Division[1].Number TYPE NameValue VALUE 'Premiership'; 
CREATE FIELD OutputRoot.XMLNS.TestCase.Division[1].Result[1].Number TYPE NameValue VALUE '1'; 
CREATE FIELD OutputRoot.XMLNS.TestCase.Division[1].Result[1].Home TYPE Name; CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[1].Result[1].Home NAME 'Team' VALUE 'Liverpool' ; 
CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[1].Result[1].Home NAME 'Score' VALUE '4'; 
CREATE FIELD OutputRoot.XMLNS.TestCase.Division[1].Result[1].Away TYPE Name; CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[1].Result[1].Away NAME 'Team' VALUE 'Everton'; 
CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[1].Result[1].Away NAME 'Score' VALUE '0'; 
CREATE FIELD OutputRoot.XMLNS.TestCase.Division[1].Result[2].Number TYPE NameValue VALUE '2'; 
CREATE FIELD OutputRoot.XMLNS.TestCase.Division[1].Result[2].Home TYPE Name; CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[1].Result[2].Home NAME 'Team' VALUE 'Manchester United'; 
CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[1].Result[2].Home NAME 'Score' VALUE '2'; 
CREATE FIELD OutputRoot.XMLNS.TestCase.Division[1].Result[2].Away TYPE Name; CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[1].Result[2].Away NAME 'Team' VALUE 'Arsenal'; 
CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[1].Result[2].Away NAME 'Score' VALUE '3'; 
CREATE FIELD OutputRoot.XMLNS.TestCase.Division[2].Number TYPE NameValue VALUE '2'; CREATE FIELD OutputRoot.XMLNS.TestCase.Division[2].Result[1].Number TYPE NameValue VALUE '1'; 
CREATE FIELD OutputRoot.XMLNS.TestCase.Division[2].Result[1].Home TYPE Name; CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[2].Result[1].Home NAME 'Team' VALUE 'Port Vale'; 
CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[2].Result[1].Home NAME 'Score' VALUE '9' ; 
CREATE FIELD OutputRoot.XMLNS.TestCase.Division[2].Result[1].Away TYPE Name; CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[2].Result[1].Away NAME 'Team' VALUE 'Brentford'; 
CREATE LASTCHILD OF OutputRoot.XMLNS.TestCase.Division[2].Result[1].Away NAME 'Score' VALUE '5'; 
```
#### Result
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<TestCase description="This is my TestCase"> 
<Identifier>ES03B305_T1</Identifier> 
<Sport>Football</Sport> 
<Date>01/02/2000</Date> 
<Type>LEAGUE</Type> 
<Division Number="Premiership"> 
<Result Number="1">
<Home> <Team>Liverpool</Team> <Score>4</Score> </Home> 
<Away> <Team>Everton</Team> <Score>0</Score> </Away> </Result> 
<Result Number="2"> 
<Home> <Team>Manchester United</Team> <Score>2</Score> </Home> 
<Away> <Team>Arsenal</Team> <Score>3</Score> </Away> </Result> </Division> <Division Number="2"> 
<Result Number="1"> 
<Home> <Team>Port Vale</Team> <Score>9</Score> </Home> 
<Away> <Team>Brentford</Team> <Score>5</Score> </Away> </Result> </Division> </TestCase>
```

