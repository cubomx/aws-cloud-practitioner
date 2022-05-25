# Security & Compliance
**Shared Responsibility Model**
- AWS: security of the cloud
    - Managed services
    - Protecting infra
- Customer: security in the cloud
    - Data
    - Network config

Shared controls:
- Path management, config management, awareness & training

## DDoS Protection
**AWS Shield Std**:
- Free, enablef by default
- Protect website & apps
- Against: 
    - SYN/UDP Floods
    - Reflection attacks
    - Layer 3/4 attacks
**AWS Shield Advanced**: 24/7 Premium DDoS Protection
- $3k per month per org
- Protect against more sophisticated attacks:
    - EC2
    - ELB
    - CloudFront
    - Global Accelerator
    - Route S3
- 24/7 support
- Protect agains higher fees during usage spikes due to DDoS
**AWS WAF**: filter specific reqs based on rules
- Protect from common web exploits (Layer 7, HTTP)
- Deploy on ALB, API Gateway, CloudFront
- Define Web ACL
    - Filtering IP addresses, HTTP headers, HTTP body, or URI strings
    - Protect SQL injection/ Cross-Site Scripting (XSS)
    - Szie contraints, block countries
    - Ocurrence of events (**Rate-based rules**)
**CloudFront & Route 53**: 
- availability protection using global edge net
- Combined with Shield, provides attack mitigation at the edge

## Penetration Testing
When u attack ur own infra. 8 services to test against without prior approval
- EC2 instances, NAT Gateways, ELB
- RDS
- CloudFront
- Aurora
- API Gateways
- Lambda & Lambda Edge Functions
- Lightsail resources
- Beanstalk envs

Prohibited:
- DNS zone walking via Route 53 Hosted Zones
- DoS, DDoS, Simulated DoS, Simulated DDoS
- Port, protocol or request flooding

## Encryption
**AWS KMS** (Key Management Service): u don't have the keys
opt-int:
- EBS volumes: encrypt them
- S3 buckets: server-side encryption of objs
- RDS DB, Redshift DB, EFS drives: encryption of data
Autoencryption enabled:
- CloudTrail logs
- S3 Glacier

**CloudHSM**
- AWS provisions encryption **hardware**
- Dedicated Hardware (HSM, Hardware Security Module)
- U manage encryption keys
- Tamper resistant, FIPS 140-2 Level 3

## Customer Master Keys (CMK)
- **Customer Managed CMK**:
    - Rotation policy
    - Create, Manage & used by the Customer
- **AWS managed CMK**:
    - Create, Manage & used on the Customer's behalf by AWS
    - Only AWS svcs
- **AWS owned CMK**
    - CMKs owned & managed by an AWS svc
    - To protect resources, u cannot view the keys
- **CloudHSM Keys** (custom keystore)
    - Keys from CloudHSM devices 
    - Crypto ops are perfomed within the CloudHSM cluster

## AWS Certificate Manager (ACM)
Easily to provision, manage & deploy **SSL/TLS Certificates**
- Provide in-flight encryption for websites (HTTPS)
- Free public TLS certificates
- Automatic TLS Certificate renewal
- **Integration** (load TLS certificates on svcs)

## AWS Secrets Manager (like HashiCorp Vault)
Storing secrets.
- Rotation every X days
- Automate the rotation (**Lambda**)
- Integration with **RDS** (MySQL, PostgreSQL, Aurora)
- Encrypted using **KMS**

## AWS Artifact (not a service)
Portal, for on-demand acces to **AWS compliance** & **AWS agreements**:
- **Artifact Reports**: Download **AWS Security & Compliance** docs from 3rd-party auditors
like ISO, PCI (Payment Card Industry), SOC (System & Org Control).
- **Artifact Agreements**: Review, accept & track the status of AWS agreements like
BAA (Business Associate Addendum), HIPAA (Health Insurance Portability and Accountability) for 
ind accounts or orgs

## Amazon GuardDuty
**Intelligent Threat Discovery** to protect ur account.
- ML, anomaly detection, 3rd party data.
- One click to enabled 
- **Input data**:
    - **CloudTrail Events Logs**: unusual API calls, authorized deploys
        - Management Events: create VPC subnet
        - S3 Data Events: get object, list objects, ...
    - **VPC Flow Logs**: unusual internal traffic, IP addresses
    - **DNS Logs**: compromised EC2 instances sending encoded data within DNS queries
    - **Kubernetes Audit Logs**: suspicious actvs & potential EKS cluster compromises
- Can setup **CloudWatch Event rules** to be notified (AWS Lambda or SNS)
- Can **protect against CryptoCurrency attacks**

## Amazon Inspector
Automated **Security Assessments**
- **EC2 Instances**: 
    - Analyze OS against know vulnerabilities
    - Ana.. against unintended net accesibility
    - Leveraging the **AWS SSM agent**
- **Containers push to Amazon ECR**

**Reporting & Integration** with AWS Security Hub
Findings send to **Amazon EventBridge**

What evaluates?
- Continuous scanning when needed
- Package vulnerabilities (DB of CVE)
- Net reachability 

## AWS Config
Helps with **auditing & recording compliance** of ur AWS resources
- Record configs & changes over time
- Storing config data into S3 (can be analyzed by Athena)
- It can help with:
    - *Unrestricted SSH access to my SQ*
    - *Buckets, public?*
    - *ALB config changed?*
- U can receive alerts (SNS notification)
- Regional

## Amazon Macie
Data security & data privacy svc that uses **ML & pattern matching to discover & protect ur**
**sensitive data in AWS**
- Fully managed
- Identify & alert (CloudWatch Events) about sensitive data (e.g. PII)
- Integrations: SNS, Lambda
- Buckets

## AWS Security Hub
Central sec tool to manage sec across several AWS accounts & automate sec checks
- Dashboards: current sec & compliance status
- Alerts predefined or custom from:
    - GuardDuty
    - Inspector
    - Macie
    - IAM Acces Analyzer
    - Systems Manager
    - Firewall Manager
    - Partner Network Solutions
 
 **MUST: Enable AWS Config Service**

## Amazon Detective
When other svcs (GuardDuty, Macie, Security Hub) find issues or similars and u 
want to do a deeper analysis to isolate the root cause & take action.

It **analyzes, investigates, & quickly identifies the root cause of sec issues or** 
**suspicious actvs** (using ML & graphs)

Collects & processes events from:
- VPC Flow Logs
- CloudTrail
- GuardDuty

And... It creates a unified view

## AWS Abuse
U can report abusive or illegal use of AWS:
- Spam
- Port scanning
- DoS o DDoS attacks
- Intrussion attempts
- Hosting illegal or copyrighted content
- Distributing malware

## Root user privileges
Complete access.
**U SHOULDN'T USE THIS FOR EVERYDAY TASKS**
Specific actions:
- Change account settings
- View certain tax invoices
- Close ur AWS account
- Restore IAM user permissions
- Change ur AWS Support plan
- Register as a seller in the Reserved Instance Marketplace
- MFA for S3 bucket
- SignUp for GovCloud