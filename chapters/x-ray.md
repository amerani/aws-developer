# X-Ray
- visualizing serverless apps
- find bottlenecks
- see request, response
- also downstream calls to other resources

### json flow
x-ray sdk -> x-ray daemon -> x-ray api -> x-ray console

aws sdk and aws cli can connect to xray daemon or api

### SDK
- interceptors to trace incoming http requests
- handlers for instrumenting aws sdk client uses
- http client to instrument external web services 

### Integration
- ELB
- Lambda
- API Gateway
- Elastic Compute Cloud
- Beanstalk

### Languages
- Java, Go, Node, Ruby, Python, C#
