# EBS (Elastic Block Storage)
- attached to EC2 instances
- you can create a FS or run a DB on it
- like any other block storage

## General Purpose SSD (GP2)
- balances price and performance
- 3 iops/gb upto 10,000 iops

## Provisioned IOPS SSD (IO1)
- high performance ex dbs
- greater than 10,000 IOPS

## Throughput Optimized HDD (ST1)
- cannot be boot volume 
- big data, data warehouse

## Cold HDD (SC1)
- cannot be boot volume
- low cost, infrequent workloads
- file server

## Magnetic (Standard)
- bootable
- lowest cost

## Encrypt an EBS Volume attached to EC2 

### new volumes
- create encrypted volume in same AZ as ec2
- attach to ec2 instance
- make file system
- mount

`lsblk` - show all volumes

`file -s /dev/xvdf` - check for fs

`mkfs -t ext4 /dev/xvdf` - make file system

`mkdir /filesystem && mount /dev/xvdf /filesystem` - make new dir and mount volume there

`unmount -d /dev/xvdf` - unmount volume 

### from snapshots
- volumes created from encrypted snapshots are encrypted
- unencrypted are unencrypted
- no snapshot, choose one
- take a snapshot
- detach and delete volume
- create volume from snapshot
- attach volume
- mount

### encrypting root volume
- take snapshot of root volume
- copy snapshot as encrypted
- create image (AMI) from snapshot
- launch instance with this image
