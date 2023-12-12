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
- 