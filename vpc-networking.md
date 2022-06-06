# VPC & Networking

## Virtual Private Cloud (regional)
**Subnets**: partition of network inside VPC (AZ resource)
**Route Tables** to define access to the internet & between subnets
**CIDR**: range of IP address allowed within.

## Internet Gateway
Helps to connect VPC instance to the internet
- Public Subnets have a **route to the internet gateway**
- Provide Internet Access
- HA, horizontal scaling, redudant

Allow instance in **Private Subnets** to access Internet while remaining private:
- **NAT Gateway**: AWS-managed
- **NAT instances**: (self-managed)

## Network Security
First line of security: **NACL** (Network ACL) -> A Firewall
- Controls traffic from & to subnet
- ALLOW/DENY
- Only IP addresses
- Subnet level
- Explicit allow
- Stateless

**Security Groups**: Firewall that
- Controls traffic to & from an ENI/**EC2 Instance**
- ALLOW ruless
- IP addresses & other SGs
- Automatically allowed, regardless of any rules
- Stateful

## VPC Flow Logs
- Info about iP traffic going into ur interfaces:
    - **VPC** Flow Logs
    - **Subnet** Flow Logs
    - **Elastic Network Interface** Flow Logs
- Monitor & troubleshoot connec issues
    - Conn betwen subnets
    - Conn subnet to internet
    - Conn internet to subnets
- Export to S3, CloudWatch Logs

## VPC Peering
Connect 2 VPC (using AWS net)
- Make them behave like 1 network
- CIDR mustn't overlap
- It is not a chain, you need to create direct
peering between VPCs

## VPC Endpoints
Connect to AWS services **using a private net**
- Better security
- Lower latency

Types:
- Gateway: S3 & DynamoDB
- Endpoing: rest

## Site to Site VPN
Connect an on-premises VPN to AWS
- Auto encryption
- Public internet

Arch:
- On-premises: a Customer Gateway (CGW)
- AWS: a Virtual Private Gateway (VGW)

## Direct Connect (DX)
Establish a physical conn between on-premises & AWS
- Private, secure & fast
- Takes at leat a month to establish

## Transit Gateway
Have transitive peering between 1ks of VPCs & on-premises, hub-and-spoke (star) connection
- One single Gateway
- Works with DX Gateway, VPN connections