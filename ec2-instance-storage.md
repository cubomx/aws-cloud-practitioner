# EC2 Instance Storage

## EBS
**EBS** (Elastic Block Store) Volume is a **Network Drive** you can attach to
your instances while they runs:
- Persist data.
- 1 to 1 instance (CCP level)
- Bound to specific AZ
- Free tier: 30 GB  free GP of SSD or Magnetic p/month
- Communicates through the network
- U can use snapshot to move to another
- Capacity (IOPS, GBs)
    - Billed for it
    -  U can change it
- **Delete on Termination**

## EBS Snapshots
Make a backup at a point in time.
To do the backup:
- Not neccesary to detach, but recommended

Features:
- **Archive**: 75 % cheaper; moved from the normal; 24-72 hrs to restore
- **Recycle Bin**: by default deleted snapshosts are gone, unless you specify a
retention 

## AMI
Amazon Machine Image. Customization:
- Software
- Config
- OS
- Monitoring

Faster due to pre-packaged. Built specifically for a region.

Types:
- AWS
- Own
- Marketplace

## AMI Process
1. Start the EC2 Instance & customize it
2. Stop the instance (for data integrity)
3. Build an AMI (creates an EBS snapshot)
4. Launch

## EC2 Image Builder
Automate the creation of VMs or container images:
- Creation
- Maintain
- Validate
- Test


## EC2 Instance Store
High-performance hardware disk. HD attached to the physical server.
- Better I/O performance.
- Ephemeral; storage lost if instance is stopped
- Risk of data loss if 
- Backups & Replication are your responsibility

## Elastic File System (EFS)
Managed NFS (Network file system) that can be:
- Mounted on 100s of EC2
- Shared
- Only Linux EC2 instances (multi AZ)
- HA, scalable, pretty expensive (only pay for GBs stored)

**EFS-IA** (Infrequent access):
- Cost-optimized for files not accesed every day
- Uo to 92% less than EFS Std
- If enabled, automatically passes the infrequent files to **Lifecycle Policy**

## Shared Responsibility Model
- **AWS**:
    - Infra
    - Replication for EBS & EFS
    - Replace faulty hardware
    - Not access to your data
- **Customer**:
    - Backup
    - Setting up Data encryption
    - Data
    - Risk of EC2 Instance Store

## Amazon FSx
3rd Party HP File Systems. Fully managed. 3 offerings:
- For Lustre
    - Scalable file storage for High Performance Computing
    - Linux & Cluster
    - ML, Analytics, Video Processing, Financial Modeling
    - Up to 100s GB/s, millions of IOPS, 
- For WinD File Server
    - Highly reliable, scalable
    - WinD native file shared FS
    - Support for SMB protocol & WinD NTFS
    - Integration with Microsoft AD
    - Accesed from AWS/On-premises
- For NetApp ONTAP