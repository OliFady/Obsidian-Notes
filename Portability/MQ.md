# Queues advantages

- Buffer Messages (Async)
- Batch Processing (Wait until certain amount is received)

# P2P Messaging

 - consumed only once
### Send & Forget
- Password reset messages
### Request/Reply 
- DB Query that needs to be sent back in the body
## Limitations
### State info
- changes at anytime (needs polling)
### Event Info
- Restock Node needs to access many other Services

# Publish/Subscribe
- Topic can be subscribed on by Consumers
- Broker Decouples Provider from Consumer by holding Info about Subscriptions

## Types of Data in MQ
### Query Data
- Querying current state of an order
### Business-Critical Data (Most)
- Message confirming a Payment

