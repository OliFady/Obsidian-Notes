- Local Queues are the only Queues that hold Msgs
### MQMD
- Message Descriptor Structure
### MQOPEN & MQCLOSE
- MQOPEN accesses a certain Object
- MQOD is passed into MQOPEN call describing the accessed Object
- MQOPEN can call MQGET, MQPUT, MQINQ & MQSET
### MQPUT
- Calls are returned after being placed on Queue
- MQMD is passed to MQPUT
### MQPUT1
- Performs calls MQOPEN, MQPUT & MQCLOSE
- Convenient when a Single Msg need to be put on Queue (Reply or Report)
### MQGET
- MQMD & MQGMO (Msg Options Structure) is passed to MQGET
- MQGMO passes a Correlation Identifier to specify specific Info or fail the call
### MQBEGIN
- Starts unit of works involving DB Products
### MQCMIT & MQBACK
- Commits current Unit of work
- MQBACK rolls back the current of work
### MQINQ & MQSET
- MQINQ Queries values of specific Attributes 
### MQDISC
- Disconnects Queue Manager