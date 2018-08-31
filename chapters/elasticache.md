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

## Lazy Loading
- only when necessary
- hit -> returns
- miss -> load from databse and write to cache
- miss penalty
- only requested data is cached
- node failure is not fatal
- stale data (specify TTL)

## Write-Through
- adds or updates data on writes to db
- never stale
- write penalty (fine when updating)
- node failure 
- wasted resource if data is not read