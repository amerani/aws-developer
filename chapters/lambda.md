# Lambda
- code that runs without managed servers
- event driven compute service (trigger)
- compute service in response to http request
- languages: node, java, python, c#, go
- continuous scaling (scale out, not up)
- 1 event = 1 function
- 1 event = x functions, if fanout
- aws xray for debugging

### Cost
- 1st million requests per month are free
- duration: time that code run

### Triggers
- API Gateway
- AWS IoT
- Alexa Skills Kit
- Alexa Smart Home
- CloudFront
- CloudWatch Events
- CloudWatch Logs
- CodeCommit
- Cognito Sync Trigger
- DynamoDB
- Kinesis
- S3
- SNS
- SQS

### Versioning
- publish one or more version
- has unique ARN 
- Qualified ARN: with version suffix
- Unqualified ARN: without version suffix
- published versions are immutable
- $LATEST can be mutated and saved to publish a new version

### Alias
- latest -> $LATEST
- PROD -> version x
- BlueGreen -> 50% version 1, 50% version 2
