# Intro to Cloud Computing

## Usage Case
**Requirement**: Host a website
**SysAdmin** is responsible for:
- Choosing the Data Center or Hosting Provider
- Send your requirements
- Contact back and negotiate prices

## Cloud computing
Model in which computing resource are available as a service. **On-demand delivery**
of compute power, DB storage, apps, and other IT resources.

Important characteristics:
- **On-demand & self-service**: you can lauch whenever you want without manual intervention
- **Elasticity**: scaling anytime (up/down)
- **Measured Service**: pay for/what you use

Benefits:
- Simple way to access to your services
- Instant scaling
- Pay-as-you-go pricing



## Cloud Computing Models/Types
- **SaaS**: Google Docs, Office 365, Zoom
- **PaaS**: Google App Engine, Heroky, Elastic Beanstalk
- **IaaS**: AWS, Linode, Digital Ocean, EC2 

## Deployment Models
- **Private Cloud**: used by single organization, not exposed to the public
    - Complete control
    - Security for sensitive
    - Meet specific business needs
- **Public Cloud**: cloud resources owned & operated by a 3rd party over the Internet

## Characteristics of Cloud Computing
- On-demand self-service
- Broad network access
- Share infrastructure and still have privacy & security
- Rapid elasticity & scalability

## Advantages of Cloud computing
- CapEx to OpEx
- Massive economies of scale
- Stop guessing capacity
- Increased speed & agility
- Stop maintaing datacenters
- Globally

## Problem solved by the Cloud
- **Flexibility**: change whenever you want
- **Cost-Effectiveness**: pay-as-you-go
- **Scalability**: accomodate larger loads
- **Elasticity**: scale out/in
- **HA & fault-tolerance**: build across data centers
- **Agility**

## Pricing of AWS
- **Compute**: pay for compute time
- **Storage**: pay for data stored in the Cloud
- **Data transfer OUT of the cloud**: Data transfer **IN** is free

## History of AWS Cloud
- 2002: launched internally
- 2004: launched publicly with SQS
- 2006: re-launched publicly with SQS, S3, EC2
- 2007: launched in Europe

## Global infra
- **AWS Regions**: cluster of data centers; some service/products are linked to
a specific region
- **AWS Availability Zones**: inside a region exist many AZ (2 to 6, usual 3). 
Each AZ is 1+ discrete Data Centers with redudant power, networking & connectivity
    - Separate from each other (isolated from disasters)
    - Connected with high bandwidth, ultra-low latency networking
- **AWS Data Centers**
- **AWS Edge Locations / Points of Presence**: 216 Points of Presence (205 Edge 
Locations & 11 Regional Caches) in 84 cities across 42 countries
    - Content is delivered to end users with lower latency

Where to launch an app?
- **Compliance** with data goverance & legal requirements
- **Proximity** to customers  
- **Available services** within a region
- **Pricing**

## Shared Responsibility
**Customer** is responsible for the **Security in the cloud**
**AWS** is responsible for the **Security of the Cloud**

