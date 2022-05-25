# Deploying & Managing Infra at Scale

## CloudFormation (IaC)
Declarative way of outlining your AWS Infra (like Terraform) for most resources.
After specifying, the resources will be created:
- In the **right order**
- With the **exact config**

- U will tag each resources with an ID, so u can manage cost (and estimate). U could save by using
automated deletion templates.
- Quickly to destroy & re-create infra.
- Automated generation of diagram
- Use existing templates
- Use documentation

## AWS Cloud Development Kit (CDK)
Define infra using a proga lang: Java, Python...
- Code is compiled into a CloudFormation templates
- U can deploy infra & app runtime code together

## Beanstalk
Dev centric view of deploying an app. PaaS; uses all AWS components
- Managed service (EC2/OS, capacity, deployment perfomed, LB & ASG, Monitoring & responsiveness)
- Dev focus on app code

Models:
- Single
- LB + ASG
- ASG

Support: Go, Python, PHP, Docker, Ruby...

## AWS CodeDeploy (helps in transition)
Independent. Automatically deploy app.
- Works with EC3 Instances, On-Premises Server (Hybrid)
- Must be provisioned & configured with the CodeDeploy Agent (ahead of time)

## AWS CodeCommit
Store code in VCS.
- Fully managed
- Scalable & HA
- Private, Secured, Integrated

## AWS CodeBuild
- Compiles source code
- Run tests
- Produces packages ready to be deployed

Benefits:
- Fully Managed, serverless
- HA, continuously scalable & HA
- Secure
- Pay-as-you-go

## AWS CodePipeline (CI/CD)
**Orchestrate the diff steps** to have the code auto pushed to prod
Code => Build => Test => Provision => Deploy

Benefits:
- FM
- CodeCommit, CodeBuild, CodeDeploy, Beanstalk ...
- Agility

## AWS CodeArtifact
Secure, scalable, & cost-effective **artifact management** for software dev

## AWS CodeStar
**Unified UI** to easily manage **softwared dev** activities in 1 place

## AWS Cloud9
Cloud IDE. 
- Pair programming

## AWS Systems Manager (SSM)
Manage **EC2** & **On-Premises** systems at scale:
- Get ops insights about the state of infra
- Features:
    - Patching automation
    - Run commands across servers
    - Store param config with the SSM Parameter Store
- WinD, Linux

## SSM Session Manager
Secure shell. **NO SSH access, bastion hosts, SSH keys**
- Linux, macOS, WinD
- Log data => S3/CloudWatch Logs

## AWS OpsWorks
Chef & Puppet => perform server config auto (or repetitive action)

Only provision std AWS resources (EC2 instances, DBs, LB, EBS volumes)