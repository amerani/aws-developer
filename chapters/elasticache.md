# Elasticache
improve latency and throughput for read heavy apps or compute intensive

## Memcahed 
- memory object caching system
- managed by elasticache as pool (similar to ec2 auto scaling)
- automatic node replacement and auto discovery
- allows multithreaded 
- scale cache horizontally
- no multi-AZ

## Redis
- in-memory key-value store
- supports sorted sets and lists, sorting and ranking
- persistance is first class
- elasticache supports Master/Slave replication 
- supports Multi-AZ 
- managed by elasticache as a database engine
- also pub sub
