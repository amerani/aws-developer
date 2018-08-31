# CloudFront
- CDN: deliver content based on users geographic location 

## Edge Location
- location where content is cached
- cache invalidation costs money 
- edge location > aws AZ > aws region

## Origin
- s3 bucket, ec2, elb or route 53

## Distribution
collection of edge locations

- Web Distribution: http

- RTMP: a/v media

## S3 Transfer Acceleration
- faster uploads via edge location
- network route optimization
- downloads instantly availble at edges

## Create Distribution
### origin settings
- origin domain can be ip address
- Restrict Bucket Access: all access through cloudfront
- Origin Access Identity: special AIM user for cloudfront
- Grant Read Permissions on Bucket

### cache settings
- Specify TTL depending on how frequently it changes
- Restrict Viewer Access: Signed URL or Signed Cookies for paid content
