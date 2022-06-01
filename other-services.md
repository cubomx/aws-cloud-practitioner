# Other AWS services

## Amazon WorkSpaces
**Provision WinD/Linux Desktops**
- Managed Desktop As a Service
- **Eliminates management of on-premises Virtual Desktop Infra**
- Secured with KMS
- Fast & Quickly scalable

## Amazon AppStream 2.0
Desktop App Streaming Service
- **App is delivered from within a web browser**

## Amazon Summerian 
**Create & Run VR, AR, 3D apps**
- Create 3D Models with anims

## AWS IoT Core
**Connect IoT devices to AWS**
- Serverless, secure & scalable
- Apps can communicate
- Integration with Lambda, S3, SageMaker

## Amazon Elastic Transcoder
**Convert media files** stored in S3 into media files in the **formats required by consumer playback devices** 
(phone)
- Easy
- H Scalable
- Fully managed & secure, cost effective

## AWS Device Farm
**Test web/mobile apps** against **desktop browsers, real mobile devices...**
- Concurrency
- Configure device settings
- Fully Managed

## AWS Backup
Centrally manage & automate backups.
- Fully Managed.
- On-demand, scheduled
- Point-in-time recovery
- Configurable

## Disaster Recovery Strategies
- **Backup & Restore** (cheapest)
- **Pilot Light**: minimal critical functions, at a minimal setup.
- **Warm Standby**: full version of app, at minimum size (u will need to increase cap)
- **Multi-Site**: full version, at full size.

## AWS Elastic Disaster Recovery
**Recover ur physical, virtual, & cloud-based servers into AWS**

## AWS DataSync
Move larga amount of data from on-premises to AWS.
Sync to:
- S3
- Amazon EFS
- Amazon FSx for WinD

**Replication tasks** can be scheduled and are **incremental**

## AWS Fault Injection Simulator (FIS)
Running **fault injection experiments** on AWS workloads
- Fully managed
- **Chaos Engineering**: stressing an app, observer how it responds, implements improvements