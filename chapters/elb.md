# Elastic Load Balancers

## application load balancer
- level 7 osi
- application aware
- load balance based on subdomain
- makes routing decision based on packets
- http(s) traffic
- target groups (webserver, dbs etc)

## network load balancer
- level 4 osi
- high performance
- millions of request per second, ultra-low latencies
- costly

## classic load balancer
- http/https application 
- level 7 features, X-Forward or sticky sessions
- level 4 features for tcp apps   
- 504, application is having issues (db or app)
- ip address of end user, X-Forwarded-For header
