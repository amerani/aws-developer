# elastic beanstalk
- deploys and scales your web applications
- java, php, ruby, go, docker, .net, node.js
- tomcat, passenger, puma, iis
- provisions underlying aws resources
- fully managed or user controlled
- updates, monitoring, metrics and health check

## deployment policies
### all at once
- new version to all instances at once
- system will be down while deploy is happening
- failure requires all at once

### rolling
- deploy new vesion in batches
- reduced capacity 
- not ideal for performance sensitive systems 
- failure requires rolling update

### rolling with additional batch
- launches an additional batch
- maintains full capacity
- failure requires rolling update

### immutable
- fresh group of instances in their own auto scaling group
- moved to existing scaling group if updated
- maintains full capacity
- failure requires terminating new auto scaling group
- preferred

## configuration files
- define packages, linux users, run shell commands
- yaml or json
- top level dir of app source `.ebextensions` -> `file.config` 

## rds and elastic beanstalk
- launch within (coupled)
- launch outside (decoupled)
- preferred: decouple rds and elastic beanstalk
- can tear down app without tearing down rds