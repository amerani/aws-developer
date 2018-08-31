# IAM (Identity and Access Management)
- shared access to aws account
- granular permissions
- identity federation (AD, Facebook)
- MFA
- temporary access to aws resources

## Terms
- User (end users)
- Groups (collection of users under one set of permissions)
- Roles (aws resources) ex ec2 -> s3 
- Policy: json document of permission (user, group, role)

## Tips
- Create individual IAM users: dont use root user 
- Use groups to assign permission (ex DB groups only for data resources)
- Users belong to Groups and have permissions based on group Policies
- Policies can be attached directly to users 
- Roles are for trusted entities (aws resources, 3rd party accounts) and can have policies attached like users and groups 

# EC2 with S3 Role
- create IAM Role with S3FullAcess Policy
- attach IAM Role to EC2 instance (no reboot)