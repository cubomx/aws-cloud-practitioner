# Other Compute Options

## ECS (Elastic Container Service)
Run Docker containers on AWS. 
- U provision & maintain the infra (EC2 instances)
- AWS: start/stop containers
- Integrations with the **Application Load Balancer**

## Fargate
Launch Docker containers but don't provision any infra.
- Serverless
- Runs container based on CPU/RAM u need

## ECR (Elastic Container Registry)
Private Docker Registry.
- Store your Docker images.

## Serverless
Pioneered by AWS Lambda (FaaS). U don't manage, provision or see servers.

## AWS Lambda
- Virtual functions
- Short executions
- Run **on-demand**
- Scaling is automated
- Event-driven
- Pay per request & compute time
- Integration with all AWS & many programming languages
- Easy monitoring with CloudWatch
- Time limit
- Example: CRON job (CloudWatch Events EventBridge)

**Lambda Container Image**: run Docker on top but it must implement Lambda Runtime API

## Amazon API Gateway
Expose API through HTTP (Rest).
- Fully managed service for devs to:
    - Create
    - Publish
    - Maintain
    - Monitor
    - Secure
APIs..
- Serverless & scalable
- RESTful APIs & WebSocket APIs
- Security, User authen, API keys, monitoring

## AWS Batch
Fully managed **batch processing** at any scale
- Run 100k's of computing batch jobs
- Has a start & an end
- Dynamically launch EC2 instances/Spot instances
- Provision the right amount of compute/memory
- U only schedule
- Define as **Docker images** and **run on ECS**
- No time limit

## Amazon Lightsail
For people with little cloud experience. Alternative to other advanced services.
- Virtual servers
- Storage
- DBs
- Networking

U can
- Setup notifications & monitor your Lightsail resources
- Use cases:
    - Simple web apps (use templates)
    - Websites
    - Dev/Test env

Has HA, not auto-scaling, limited AWS integrations