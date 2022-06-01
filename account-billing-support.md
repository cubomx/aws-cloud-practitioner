# Account Management, Billing & Support

## Organizations (global service)
Manage **multiple AWS accounts**
- Costs: 
    - **Consolidated Billing** (single)
    - **Aggregated usage** (price discount due to huge volumes)
    - **Pooling of Reserved EC2 instances** for shared use
- API for **automate AWS account creation**
- **Restrict account privileges** using Service Control Policies (SCP)

### Multi Account Strategies
- Per department
- Cost center
- Env (dev, prod)
- Regulatoru restrictions (SCP)
- Resource isolation
- Per-account service limits
- Logging

To do:
- Multi-Account vs 1AMVPC
- Tagging stds
- Enable CloudTrail to send logs 
- Send CloudWatch Logs to central account

All is inside an **Organizational Unit (OU)**, even the master account.

### Service Control Policies
Type of organization policy (permissions).
- Whitelist/Blacklist  **IAM actions**
- **OU** or **Account** level
- Not applied to Master
- **Service-linked roles** enable by other AWS services cannot be restricted
- Not allow anything by default (**explicit ALLOW**)

Use cases:
- Restrict access to certain services
- Enforce PCI compliance

Allowances/Restrictions at a higher level has priority.

## Consolidated Billing (AWS Org)
- **Combined usage**
    - Share the **volume pricing, reserved instances (can be turned off) & saving plan discounts**
- **One bill**

## AWS Control Tower
**Set up & govern a secure a compliant Multi-Account AWS env** based on best practices. 
- Automate setup of environment, ongoing policy management (guardrails)
- Detect policy violations, fix
- Monitor compliance (interactive dashboard)
- **Works on top of AWS Orgs**:
    - Organize accounts, implement SCPs
- Not pay, only for services enabled by

## Pricing Models
- **Pay as you go**
- **Save when you reserve**: predictable budgets, long-term
- **Pay less by using more**
- **Pay less as AWS grows**

Free services & free tier:
- IAM, VPC, Consolidated Billing
- Beanstalk, CloudFormation, ASG (pay for the resources created)

## **Compute Pricing**
### **EC2 Instances**

\# of instances, region, OS & Software, capacity, instance type & size
- **On-demand instances**
    - Min: 60secs, e/sec (Linux, WinD), e/hr (other)
- **Reserved instances**
    - Up to 75% discount, 1 or 3 years commitment
    - More discount if upfront pay
- **Spot instances**
    - Up to 90%, bid for unused capacity (you can lose instances)
- **Dedicated Host**
    - On-demand, for 1 or 3 years
- **Saving plans**: sustained usage saving

### **Lambda & ECS**
- Lambda: per call * per duration
- ECS: AWS resources & created in your app
- Fargate: vCPU & memory resources allocated you containers apps

### **S3**
- **Storage class**
- \# & size of objs: (can be based on volume)
- \# & type of requests
- Data OUT of the S3 region
- Using **S3 Transfer Acceleration & Lifecycle transitions**

**EFS** (per use, has IA & Lifecycle rules)

### EBS
- Volume type (**performance**)
- Volume in GB/month **provisionned**
- **IOPS**: 
    - General Purpose SSD (INCLUDED)
    - Provisioned IOPS SSD: Provisioneed amount
    - Magnetic: \# of requests
- **Snapshots**
    - per GB per month
- **Data transfer**
    - Otuboud, tiered for volume discounts

### RDS
- Hourly
- DB Characteristics:
    - Engine, Size, Memory class
- Purchase type:
    - On-demand
    - Reserved
- Backup can be free if DB is not full
- \# of input/output requests/(month)
- Per GB per month (additional storage)
- Deployment type
- Data out 

### CloudFront
Diff across regions.
- Aggregayed for each edge location
- Data Out
- \#HTTP/HTTPS requests

### Networking
Pay for communication between instances of different AZ. Cheaper to use the
private IP.

## Savings Plan
Commit to spend $ amount/hr for 1 or 3 yrs
- **EC2 Savings Plan**:
    - Up to 72%, commit to usage **of individual instance families in a region**
    - U can pay upfront for bigger discounts
- **Compute Savings Plan**:
    - Up to 66%, doesn't matter *family, region, size, OS, tenancy, compute options*
    - Compute options: EC2, Fargate, Lambda
    - Regions

Do this in the **Cost Explorer**

## AWS Compute Optimizer
Recommending optimal AWS resources to **reduce costs & improve performance**
- Uses ML to analyze ur **resources configs** & their **utilization CloudWatch metrics**

## Billing & Costing Tools
- **Pricing Calculator**: estimating costs
    - Cost of ur **solution arch**

### Tracking costs
**Billing Dashboard**: show actual costs, forecasts, month-to-date
- **Free Tier Dashboard**: usage of free tier

**Cost Allocation Tags**: group together resources, organizing; most detailed
- **Tags**: 
    - **AWS generated** (prefix `aws:`), auto applied 
    - **User-defined**: (prefix `user:`)
- Tags can be used to create **Resource Groups**
    - Collection of resources

**Cost & Usage Reports**
Most **comprehensive** set of **AWS cost & usage data avilable** (GRANULAT)
- Addit metadata, pricing, reservations
- Usage by an account, IAM users (hourly, daily) & activation of cost allocation tags
- Integration: Athena, RedShift, QuickSight

**Cost Explorer**: visualize, understand, & manage ur **AWS costs & usage over time**
- Create custom reports
- High level, hourly & resource level
- Choose an optimal **Savings Plan**
- **Forecast usage up to 12 months based on previous usage**

### Monitoring Costs
**Billing Alarms**: Simple alarm
Billing data:
- Stored in **CloudWatch us-east-1**
- Overall **worldwide AWS Costs**
- Actual cost


**Budgets**: **send alarms** when costs **exceeds the budget** (or foreacts)
- Types: Usage, Cost, Reservation
- Up to 5 SNS Notifications
- Filter
- Same options as **AWS Cost Explorer**
- 2 budgets are free

## Trusted Advisor
Analyze ur AWS accounts & provides recommendation on:
- **Cost optimization**
- **Performance**
- **Security**
- **Fault Tolerance**
- **Service limits**

7 Core Checks (Basic, Dev Support Plans)
- S3 **Bucket Permissions**
- **Security Groups**, - Ports, Unrestricted
- **IAM Use** (1 IAM User min)
- **MFA** on **Root Account**
- **EBS Public Snapshots**
- **RDS Public Snapshots**
- **Service Limits**

Full Checks (Business):
- All in the 5 categories
- Ability to set **CloudWatch alarms** when reaching limits
- **Programmatic access** using **AWS Support API**

## AWS Support Plans Pricing (Incremental)
Qualify for diff plan depending on spend.
**Basic**:
- **Customer Service & Communities** 24x7
- **AWS Personal Health Dashboard**

**Developer**:
- **Business hours email access** to Cloud Support Associates
- Unlimited cases, 1 primary contact

**Business**: production workloads
- **24x7 phone, email & chat access** to Cloud Support Associates
- Unlimited cases, unlimited contacts
- Access to Infra Event Management for **additional fee**
- **Production system imparied, response time**:< 4 hrs **Prodcution system down**: < 1 hr

**Enterprise On-Ramp**: production or business critical workloads
- Access to a pool of **Technical Account Managers** (TAM)
- Online training with self-paced labs
- **Concierge Support Team** (billing & account best practices)
- **Infra Event Management, Well-Architected & Operations Reviews**
- **Business-critical system down**: < 30 min

**Enterprise**: Critical Workloads
- Designated **TAM**
- **Business-critical system down**: < 15 min