# Advanced Identity

## AWS STS (Security Token Service)
Create **temporary, limited-privileges credentials** to access ur AWS Resources.
- Short-term, configurable
- Use cases:
    - **Identity federation**: users in external systems
    - **IAM Roles for cross/same account access**
    - **IAM Roles for EC2**

## Amazon Cognito
**Identity for ur Web/Mobile apps users**

## Directory Services
**AWS Managed Microsoft AD**:
- Create ur own AD in AWS.
- Establish trust connections.

**AD Connector**
- Proxy to redirect to on-premise AD, MFA


**Simple AD** (NOT Microsoft)
- AD-compatible on AWS
- Not on-premise

## AWS SSO
Access **multiple accounts & 3rd party business apps**
- Integrated with **AWS Organizations**