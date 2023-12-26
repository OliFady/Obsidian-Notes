- A clever base case makes Recursion simpler

```java
foo(n){
if(n==1)
return 1;
else
return n + foo(n-1);
}

```
## Recursion Phases

- Pre -> n+
- Recursion -> foo(n-1)
- Post -> checking the Base case 