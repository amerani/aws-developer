# DyanmoDB
- nosql
- single digit millisecond laltency
- document and key-value data model
- ssd storage
- spread across 3 locations

### Eventually Consistent Reads
- all copies are updated within a second
- re-read should get updated data
- best read performance

### Strongly Consistent Reads
- all successful writes prior to the read

## Terms
- tables
- items (row)
- attributes (column)
- key(name), value(data)
- json, html, xml documents

## Partition Primary Keys
- unique attr ex userId
- hashed to determine partition/physical location
- unique

## Composite Primary Keys
- combination of partition and sort key
- ex same user inserting multiple records
- sort key would be some other attribute like timestamp
- stor

## Access Control
- IAM user
- IAM role
- Condition to IAM Policy (restrict to owner of data record)
`dynamodb:LeadingKeys`

### CLI
`aws dynamodb get-item --table-name t --key '{"Id":{"N": 2}}'`

## Local Secondary Index
- at creation time
- same partition key
- different sort key

## Global Secondary Index
- flexible creation
- different partition key
- different sort key

## Query API
- find item using only primary key (ex userId)
- use optional sort key and value (ex timestamp 7 days)
- `ProjectionExpression` to filter attributes
- sorted by sort key, ascending order
- reverse order `ScanIndexForward = false`
- more efficient

## Scan API
- examine every item
- default all data attributes
- `ProjectionExpression` to filter attributes
- smaller page size
- parallel scans, by dividing in segments (not recommended)

## Provisioned Throughput
- measured in Read or Write Capacity Units
- 1WCU = 1 x 1kb write per sec
- 1RCU = 1 x strongly consistent read 4kb per sec
- 1RCU = 1 x eventually consistent read 4kb per sec

### read example:  
strongly consistent read 80 items per second  
item = 3kb  

rcu per read = size of item / 4kb = 3kb/4kb = 0.75 ~= 1  
total rcu = rcu per read * reads per second = 1*80 = 80 rcu  

eventually consistent = 80 / 2 = 40 rcu

### write example:
write 100 items per sec  
item = 512 bytes  

wcu per write = 512 bytes/1kb = 0.5 ~= 1  
total wcu = 100*1 = 100 wcu

## DynamoDB Accelerator (DAX)
- fully managed, clustered, in-memory cache
- 10x read performance
- write through caching service
- allows apps to query DAX cluster 
- reduces provisioned read capacity
- *eventually consistent* reads only