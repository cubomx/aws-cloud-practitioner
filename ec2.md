# Elastic Compute Cloud
IaaS. Consists of: 
- VMs (EC2)
- Storing data on VDrives (EBS)'+   yu io
- Elastic Load Balancer
- Auto-scaling group (ASG)

## EC2 options
- OS: Linux, WinD, MacOS
- CPU: Cores
- RAM
- Storage space:
    - Net-attached (EBS & EFS)
    - Hardware (EC2 Instance Store)
- Net card: speed of card, public IP address
- Firewall rules: security group
- Boostrap script (at launch): EC2 User Data (sudo root)
    - Launching cmds  when a machine starts
    - Only run at the first start
    - Tasks: 
        - Install updates
        - Install software
        - Download common files

## EC2 Instance Types
Convention name, e. g: `m5.2xlarge`
- **m**: instance class
- **5**: generation
- **2xlarge**: size within the instance class

**General Purpose**: diversity of workloads (web servers/code repos).
    - Balance between *compute, memory & networking*

**Compute Optmizied**: high perfomance processors.
    - Batch
    - Media transconding
    - HP web servers/computing
    - Scientific modeling & ML
    - Dedicated gaming servers

**Memory Optimized**: process large data sets in memory
    - HP, RDB NonRDB
    - Distributed web scale
    - In-memory DBs optimized for BI
    - Real-time processing of unstruct data

**Storage optimized**: high, sequential RW access to large data sets on local 
storage.
    - High Freq OLTP Systems
    - RDBs & NonRDBs
    - Cache for in-memory DBs (Redis)
    - Data Warehousing

## Security Groups
Control how traffic is allowed in/out of EC2 instances
    - Allow rules
    - Reference by IP/SecG

Regulate:
    - Access to ports
    - Authorized IP ranges (IPv4/IPv6)
    - Control inbound/outbound net

Good to know:
- Many to many
- Locked down to a region/VPC combination
- EC2 won't see any blocked traffic
- "Connection refused" -> App error or not launched
- "Time out" -> SG issue
- In traffic is blocked by default
- Out traffic is allowed

Ports: 
- 21: FTP 
- 22: SFTP 
- 3389: RDP (Remote Desktop Protocol) Log into WinD instance

**EC2 Instance Connect** connect to all kinds of OS using SSH. *ONLY IN AMZON NX2*

**EC2 Instance Role**: link to IAM roles

## Purchasing options
- **On-demand**: billing p/s (Linux/WinD) or p/hr (other OS)
- **Reserved** (1 or 3 years): commit to a specific instance type
    - Long workloads
    - **Convertible Reserved Instances**: flexible type/OS/scope/tenancy
    - U can buy/sell themin the RI Marketplace
- **Saving Plans** (1-3 years): commit to a amount of usage
- **Spot Instances**: short worklaods, cheap, can lose instances
    - U put a MAX price you wish to pay
    - Distributed workloads
    - With flexible start & end time
- **Dedicated Hosts**: book an entire physical server
    - Compliance requirements
    - 2 options (on-demand or Reserved)
- **Dedicated Instances**: no other costumers will share hardware
- **Capacity Reservations**: reserve capacity in a specific AZ for any duration