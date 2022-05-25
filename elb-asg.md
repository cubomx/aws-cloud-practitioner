# Elastic Load Balancing & Auto Scaling Groups
**Scalability** an app can handle greater loads by adapting
    - Vertical
        - Limit: hardware
    - Horizontal (elasticity)

**High Availability** running in multiple zones in case of failure.

**Agility**: quickly to get the resources

## Load Balancing
Servers that forward internet traffic to multiple servers downstream.
- Spread load
- Expose a single point of access (DNS)
- Handle failures of downstream instances
- HA across zones
- SSL termination (HTTPS)
- Health checks

Kinds:
- App LB (HTTP/HTTPS) (Layer 7)
- Network LB (ultra-HP, allows TCP) (Layer 4)
- Classic LB (Layer 4 & 7)

## Auto Scaling Group
Load can change. Having a min & max # of machines running.
- Register new instances to a LB
- Replace unhealthy instances

## Strategies
- Manual Scaling
- Dynamic Scaling
    - **Simple/Step Scaling**: 
    - **Target Tracking Scaling**: mantain a certain usage
    - **Scheduling Scaling**: usage patterns
- Predictive Scaling
    - Uses ML