# IAM: Users & Groups
IAM: Identity and access management (global service)

A **root account** shouldn't be used/shared, you only create users

Permission: users/groups can be assigned JSON documents (*policies*). Don't give
more permissions than a user needs.

## Policies
**Inline policy**: policy attached to a user.

### Structure
```json
{
    "Version": "",
    "Id": "", // optional, identifier for the policy
    "Statement": [
        {
            "Sid": "1", // statement identifier
            "Effect": "Allow", // access (Allow, Deny)
            "Principal": { // which accounts/user/role is applied
                "AWS": [""]
            },
            "Action": [ // list of actions to be applied the effect
                "s3:GetObject",
                ""
            ],
            "Resource": [ // list of resources to be applied
                "arn.aws:s3:::mybucket/*"
                ]
        }
    ]
}
```

Optionally, you can put conditions.

You can use the **AWS console** to create policies:
- Visual editor
- JSON

## Password Policy
Having a higher level of security for your account:
- Min password length
- Specific character types
- Allow IAM users to reset their passwords
- Password expiration 
- Prevent password re-use

## Multi Factor Authentication
MFA = *password you know* + *security device you own*

You can use:
- App (Google Authenticator/Authy)
- Universal 2nd Factor (U2F) Security Key (YubiKey)
- Hardware Key Fob MFA Device
- Hardware Key Fob MFA Device for AWS GovCloud (US)

## Access AWS
We have 3 options:
- **AWS Management Console** (MFA)
- **AWS CLI**: access keys
- **AWS SDK** (code): access keys 

**Access Keys** generated by the AWS Console

Configure account:
```aws
aws configure
```

## IAM Roles for Services
Give *AWS services* permissions to perform actions on your behalf.
Common roles:
- EC2 Instance Roles
- Lambda Function Roles
- Roles for CloudFormation

## IAM Security Tools
- **IAM Credentials Report** (account-level):
    - Lists all account's users & status of their creds
- **IAM Access Advisor** (user-level):
    - Shows the service permissions granted & when those svcs were last accesed
    - Revise your policies

## Best Practices
- Root account just for AWS account setup
- 1 physical user = 1 AWS user
- MFA
- Strong pass policy
- Assign permissions to groups
- Use Access Keys for CLI/SDK 
- No share user or keys
- Use roles for permissions

AWS responsible for infra, you for the data and how you use it.
