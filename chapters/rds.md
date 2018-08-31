# RDS (Relational Database Service)

### OLTP (Online Transaction Processing)
- RDS (SQL, MySQL, PostgreSQL, Aurora)
- record given an id

### OLAP (Online Analytics Processing)
- Redshift
- aggregation across given large number records

### Elasticache
fast in-memory frequently accessed data cache vs slow disk based data stores  
create db: database instance/server and database itself

ec2 in one security group and rds in another security group
- add inbound rule for rds security group
- open db port to ec2 security group 

## Backups
### automated (daily snapshot)
- default, free s3 storage for backups
- deleted when instances are deleted

### database snapshots
- user initiated
- remain after instances are deleted

### restore
- new instance + new dns endpoint

### encryption
- AWS KMS
- backups, read replicas, snapshots are also encrypted
- manual encrypted copy of snapshots to launch instances from

## Multi-AZ
- synchronous write replication to rds instance in different AZ
- disaster recovery
- automatic failover
- hostname == dns endpoint, aws swaps dns entry during failover
- failover (planned maintenance, instance failure, AZ outage)
- no performance gains

## Read Replicas
- asynchronous write replication
- 5 read replicas per prod db, also read replicas of read replicas
- allows scaling out for reads
- read replicas can be in different AZ or different region
- must have automatic backups turned on
- read replica have its own dns endpoint
- multi AZ + read replicas can w ork for same source db
- read replicas can be promoted to its own db
