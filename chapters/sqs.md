# SQS
- distributed queue system
- ec2 can poll the queue to consume messages
- sqs is PULL basesd system
- upto 256KB of text 
- visibility timeout: time message not visible until reader is processing (30 sec - 12 hours)
- retention period is 4 days

## Standard Queues
- default
- best effort ordering
- nearly unlimited number of transactions

## FIFO Queues
- guarantees ordering
- 300 transations per second

## Long Polling
- doesnt return until message arrives in queue or timeout
- vs short poll which return immediately