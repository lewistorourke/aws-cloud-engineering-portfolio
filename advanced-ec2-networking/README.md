
## EC2 Placement Groups Hands-On

### Project Overview

In this hands-on project, I created and explored Amazon EC2 Placement Groups to control how EC2 instances are physically placed on AWS infrastructure.

This exercise demonstrated how placement strategies can be used to optimise for performance, fault tolerance, and workload isolation depending on application requirements.

---

## Objectives

- Create EC2 Placement Groups
- Understand the three placement strategies
- Configure Cluster Placement Groups
- Configure Spread Placement Groups
- Configure Partition Placement Groups
- Launch EC2 instances into specific placement groups
- Understand performance and availability trade-offs

---

## AWS Services Used

- Amazon Elastic Compute Cloud (EC2)
- EC2 Placement Groups

---

## Practical Tasks Completed

### Navigated to Placement Groups

Accessed the placement group configuration by navigating to:

- EC2 Console
- Network & Security
- Placement Groups
- Create Placement Group

### Created a Partition Placement Group

Created a placement group named `my-distributed-group` using the **Partition** strategy.

Configured:

- Number of partitions: 2

This strategy distributes instances across multiple logical partitions, each placed on separate hardware.

### Created a Spread Placement Group

Created a placement group named `my-critical-group` using the **Spread** strategy.

Configured:

- Spread level: Rack (No restrictions)

This strategy places each instance on distinct hardware to minimise the impact of a single hardware failure.

### Created a Cluster Placement Group

Created a placement group named `my-high-performance-group` using the **Cluster** strategy.

This strategy places instances physically close together within the same Availability Zone to achieve low latency and high network throughput.

### Launched Instances into Placement Groups

During EC2 instance creation, navigated to:

- Launch Instance
- Advanced Details
- Placement Group

Selected the desired placement group to control where the instance was deployed.

---

## Placement Strategy Summary

### Cluster Placement Group

Optimised for:

- Low network latency
- High throughput
- High-performance computing workloads

Common use cases:

- Big data analytics
- HPC applications
- Distributed databases

### Spread Placement Group

Optimised for:

- Maximum fault isolation

Common use cases:

- Critical applications
- Small numbers of important instances

### Partition Placement Group

Optimised for:

- Large distributed systems
- Reduced blast radius

Common use cases:

- Hadoop
- Kafka
- Cassandra

---

## Security and Availability Concepts Demonstrated

- Fault Isolation
- High Availability
- Infrastructure Resilience
- Low-Latency Networking
- Hardware Separation
- Workload Distribution

---

## Key Lessons Learned

- Placement Groups control how EC2 instances are physically placed on AWS infrastructure.
- Cluster placement groups provide the highest network performance.
- Spread placement groups maximise hardware isolation.
- Partition placement groups reduce the impact of hardware failures on distributed systems.
- Placement Groups can significantly improve application performance and resilience when used appropriately.

---

## Skills Demonstrated

- EC2 Infrastructure Design
- Placement Group Configuration
- High Availability Architecture
- Performance Optimisation
- Fault Tolerance Planning
- AWS Networking Concepts

---

## Screenshots

### Partition Placement Group
![Partition Placement Group](screenshots/partition-placement-group.png)

### Spread Placement Group
![Spread Placement Group](screenshots/spread-placement-group.png)

### Cluster Placement Group
![Cluster Placement Group](screenshots/cluster-placement-group.png)

---

## Outcome

Successfully created and configured Cluster, Spread, and Partition Placement Groups and learned how each strategy can be used to optimise EC2 deployments for performance, resilience, and workload isolation.

---
## Elastic Network Interfaces (ENI) Hands-On

### Project Overview

In this hands-on project, I explored Amazon Elastic Network Interfaces (ENIs), which act as virtual network cards within an AWS Virtual Private Cloud (VPC).

This exercise demonstrated how ENIs provide network connectivity to EC2 instances and how they can be detached and reattached to different instances to support rapid failover and high availability.

---

## Objectives

- Understand what an Elastic Network Interface (ENI) is
- Review the attributes associated with an ENI
- Create ENIs independently from EC2 instances
- Attach and detach ENIs from EC2 instances
- Understand how ENIs support failover
- Learn Availability Zone constraints

---

## AWS Services Used

- Amazon Elastic Compute Cloud (EC2)
- Elastic Network Interfaces (ENI)
- Amazon Virtual Private Cloud (VPC)

---

## Practical Tasks Completed

### Reviewed ENI Fundamentals

Studied how Elastic Network Interfaces act as virtual network cards that provide EC2 instances with network connectivity.

ENIs are logical networking components that exist within a VPC and can also be used by AWS services beyond EC2.

### Examined ENI Attributes

Reviewed the core attributes that an ENI can contain:

- Primary private IPv4 address
- One or more secondary private IPv4 addresses
- One Elastic IP address per private IPv4 address
- One public IPv4 address
- One or more security groups
- MAC address

### Created ENIs Independently

Learned that ENIs can be created separately from EC2 instances and attached later as needed.

### Attached and Moved ENIs Between Instances

Explored how ENIs can be detached from one EC2 instance and attached to another.

This capability is particularly useful for:

- High availability
- Rapid failover
- Preserving IP addresses and security configurations

### Reviewed Availability Zone Constraints

Confirmed that ENIs are tied to a specific Availability Zone.

This means:

- An ENI can only be attached to EC2 instances in the same Availability Zone
- ENIs cannot be moved across Availability Zones

### Understood Failover Use Case

Reviewed a scenario where an ENI is moved from one EC2 instance to another.

This allows services to recover quickly while retaining:

- Private IP addresses
- Elastic IP addresses
- Security groups
- Network identity

---

## Networking Concepts Demonstrated

- Virtual Network Interfaces
- Private and Public IPv4 Addressing
- Elastic IP Address Association
- Security Group Attachment
- High Availability
- Failover
- Availability Zone Boundaries

---

## Key Lessons Learned

- ENIs function as virtual network cards within a VPC.
- EC2 instances rely on ENIs for all network connectivity.
- ENIs can be created independently and attached dynamically.
- Moving an ENI to another instance is an effective failover mechanism.
- ENIs retain IP addresses and security group configurations.
- ENIs are restricted to a single Availability Zone.

---

## Skills Demonstrated

- VPC Networking Fundamentals
- ENI Configuration
- IP Address Management
- Security Group Association
- High Availability Design
- Failover Planning

---
---
## Outcome

Successfully explored Elastic Network Interfaces and learned how they provide network connectivity, preserve network identity, and enable rapid failover by moving interfaces between EC2 instances.

---
## Elastic Network Interfaces (ENI) Attachment and Failover Hands-On

### Project Overview

In this hands-on project, I created a secondary Elastic Network Interface (ENI), attached it to an EC2 instance, and then detached and reattached it to another EC2 instance.

This exercise demonstrated how ENIs can preserve network identity and be moved between instances to support rapid failover and high availability.

---

## Objectives

- Launch multiple EC2 instances
- Identify the default network interfaces attached to each instance
- Create a secondary Elastic Network Interface
- Attach the ENI to an EC2 instance
- Verify multiple ENIs on a single instance
- Detach the ENI and reattach it to another instance
- Understand how ENIs enable failover

---

## AWS Services Used

- Amazon Elastic Compute Cloud (EC2)
- Elastic Network Interfaces (ENI)
- Amazon Virtual Private Cloud (VPC)

---

## Practical Tasks Completed

### Launched Two EC2 Instances

Created two EC2 instances.

Each instance was automatically assigned:

- One primary Elastic Network Interface
- A unique Interface ID
- A primary private IPv4 address

### Reviewed Existing Network Interfaces

Selected each EC2 instance and navigated to:

- EC2 Console
- Instances
- Select Instance
- Networking Tab

Confirmed that each instance had one default ENI attached.

### Created a Secondary ENI

Created a new network interface named `DemoENI` by navigating to:

- EC2 Console
- Network & Security
- Network Interfaces
- Create Network Interface

### Attached ENI to the First Instance

Attached `DemoENI` to the first EC2 instance.

After attachment, the instance contained:

- Primary ENI
- Secondary ENI (`DemoENI`)

This provided the instance with an additional private IPv4 address.

### Verified Multiple Network Interfaces

Returned to the instance’s Networking tab and confirmed that two network interfaces were now attached.

### Detached the ENI

Detached `DemoENI` from the first EC2 instance.

### Reattached the ENI to the Second Instance

Attached the same ENI to the second EC2 instance.

Verified that the network interface and its associated IP configuration moved successfully.

---

## Networking Concepts Demonstrated

- Elastic Network Interfaces (ENIs)
- Secondary Private IPv4 Addresses
- Dynamic Network Attachment
- Interface Mobility
- High Availability
- Failover
- Network Identity Preservation

---

## Failover Explanation

Failover is the process of transferring a workload or network identity from one system to another when the original system becomes unavailable.

In this lab:

- The ENI retained its IP addresses and security groups
- The ENI was detached from one EC2 instance
- The ENI was attached to another EC2 instance
- Services could continue using the same network identity

This enables fast recovery without reconfiguring DNS, IP addresses, or firewall rules.

---

## Key Lessons Learned

- Each EC2 instance has a default primary ENI.
- Additional ENIs can be created independently.
- ENIs can be attached and detached dynamically.
- Moving an ENI between instances is an effective failover mechanism.
- ENIs preserve IP addresses and security group associations.
- This approach reduces downtime and simplifies recovery.

---

## Skills Demonstrated

- EC2 Networking Administration
- ENI Creation and Management
- Secondary IP Configuration
- High Availability Design
- Failover Implementation
- AWS Infrastructure Troubleshooting

---
---

## Outcome

Successfully created a secondary Elastic Network Interface, attached it to one EC2 instance, and moved it to another instance to demonstrate how AWS supports rapid failover and network identity preservation.

---
## EC2 Hibernate Hands-On

### Project Overview

In this hands-on project, I configured Amazon EC2 Hibernate and observed how an EC2 instance can be paused and later resumed without performing a full operating system restart.

This exercise demonstrated how AWS saves the contents of memory (RAM) to the encrypted root EBS volume, allowing applications and processes to continue exactly where they left off.

---

## Objectives

- Launch an EC2 instance with hibernation enabled
- Configure encrypted EBS storage
- Ensure the root volume is large enough to store RAM contents
- Connect to the instance using the terminal
- Run the `uptime` command to measure system uptime
- Hibernate the instance
- Resume the instance and verify uptime continuity

---

## AWS Services Used

- Amazon Elastic Compute Cloud (EC2)
- Amazon Elastic Block Store (EBS)

---

## Practical Tasks Completed

### Launched an EC2 Instance with Hibernation Enabled

Created an EC2 instance and enabled hibernation by navigating to:

- EC2 Console
- Launch Instance
- Advanced Details
- Enable Hibernation Behaviour

### Enabled Encrypted Storage

Configured the root EBS volume with encryption enabled.

This is required because AWS stores the contents of RAM on the encrypted root volume during hibernation.

### Verified Storage Capacity Requirements

Confirmed that the root volume was large enough to store:

- The operating system
- Installed applications
- The full contents of system memory (RAM)

### Connected to the EC2 Instance

Connected to the instance using:

- EC2 Instance Connect
- SSH terminal

### Checked System Uptime

Executed the following command:

```bash
uptime
```

This command displays how long the operating system has been running since the last reboot.

### Hibernated the EC2 Instance

Placed the instance into the Hibernate state.

AWS performed the following actions:

- Saved the contents of RAM to the encrypted root EBS volume
- Powered off the instance
- Preserved the operating system state

### Restarted the EC2 Instance

Started the instance again after hibernation.

### Verified Uptime Persistence

Ran the `uptime` command again and observed that the uptime continued from the previous session.

This confirmed that the operating system was not rebooted and resumed from its previous state.

---

## Infrastructure Concepts Demonstrated

- EC2 Hibernation
- Memory State Preservation
- Encrypted Root Volumes
- EBS Persistence
- Faster Instance Recovery
- Stateful Resume

---

## Key Lessons Learned

- EC2 Hibernate saves the contents of RAM to the encrypted root EBS volume.
- The operating system resumes exactly where it left off.
- Applications and processes remain in memory.
- The `uptime` command confirms whether a system reboot occurred.
- Root storage must be encrypted and large enough to store memory contents.
- Hibernation provides faster recovery than a full restart.

---

## Skills Demonstrated

- EC2 Advanced Configuration
- EBS Encryption Configuration
- Linux Command-Line Verification
- Instance Lifecycle Management
- Stateful Infrastructure Design
- AWS Cost Optimisation

---
---

## Outcome

Successfully configured Amazon EC2 Hibernate and verified that an instance could be paused and resumed without rebooting, preserving system memory and application state.

---
