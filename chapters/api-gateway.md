# API Gateway
- managed service to publish, maintain, monitor and secure apis
- front door to other aws services (lambda, ec2, etc)
- exposes HTTPS endpoint
- access control and tracking using API key
- throttle
- versioning
- define resource and nested resources (url paths)

## resource features
- select HTTP methods
- set security
- choose target 
- set request response transformations
- aws domain by default, allows custom domains
- free ssl/tls certs from aws certificate manager
- api caching
- same origin policy (server can relax this using cors)
- can import from swagger v2 definitions

## swagger import 
- create new with POST swagger body
- update exiting with PUT swagger body
- update can be overrite or merge

## throttling
- steady-state 10,000 requests per second
- max concurrent is 5000 across all apis
- 429 Too Many Request 
- charges for upping throttling limits

*millisecond concurrency*

10,000 req in one second (10 req per millisec) -> OK

10,000 req in first millisec -> serves 5000 and throttle rest

5000 req first ms, 5000 req spread for 999 ms -> OK
