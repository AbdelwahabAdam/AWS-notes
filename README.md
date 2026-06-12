# AWS Cloud Practitioner — Study Guide

A consolidated reference of cloud computing concepts, AWS fundamentals, and key definitions from the AWS Cloud Practitioner curriculum (KodeKloud).

---

## Table of Contents

1. [AWS Service Basics](#aws-service-basics)
2. [Cloud Computing Fundamentals](#cloud-computing-fundamentals)
3. [Traditional IT vs Cloud Computing](#traditional-it-vs-cloud-computing)
4. [Cloud Deployment Models](#cloud-deployment-models)
5. [Amazon Web Services (AWS) Overview](#amazon-web-services-aws-overview)
6. [AWS Core Service Categories](#aws-core-service-categories)
7. [Ways to Interact With AWS](#ways-to-interact-with-aws)
8. [Benefits of Cloud Computing](#benefits-of-cloud-computing)
9. [AWS Economic & Pricing Models](#aws-economic--pricing-models)
10. [Cloud Design Principles](#cloud-design-principles)
11. [Glossary of Key Terms](#glossary-of-key-terms)

---

## AWS Service Basics

### S3 — Simple Storage Service

**Amazon S3** is object storage built to store and retrieve any amount of data from anywhere.

| Term | Definition |
|------|------------|
| **S3 Bucket** | A container for storing objects (files) in Amazon S3. Each bucket has a globally unique name. |
| **ARN (Amazon Resource Name)** | A unique identifier for AWS resources. Format: `arn:partition:service:region:account-id:resource`. Used in IAM policies, SNS topics, and cross-service references. |
| **Object URL** | A direct link to an S3 object. If the bucket/object is configured for public access, the URL opens the object without authentication. |

### EC2 — Elastic Compute Cloud

**Amazon EC2** provides resizable virtual servers (instances) in the cloud. You choose the instance type, OS, and configuration, and pay for compute capacity by the hour or second.

### VPS — Virtual Private Server

A **Virtual Private Server** is a virtualized server that acts like a dedicated machine within a shared physical host. In AWS, EC2 instances are a form of VPS — isolated compute environments with their own CPU, memory, storage, and network.

---

## Cloud Computing Fundamentals

### Definition

**Cloud Computing** is the **on-demand delivery of IT resources** over the internet with pay-as-you-go pricing. Core resource types include:

- **Compute power** — processing capacity (CPU/RAM)
- **Application hosting** — running apps without managing underlying hardware
- **Database services** — managed or self-managed data stores
- **Networking** — connectivity, load balancing, DNS, and content delivery
- **Storage** — disk and object storage
- **Security & access control** — identity, encryption, and compliance
- **IT management & governance** — monitoring, logging, and policy enforcement
- **Scaling, abstraction, and high availability** — automatic scaling and fault tolerance
- **Data migration** — moving workloads to and within the cloud

### Client-Server Model

Cloud computing operates on a **client-server architecture**:

```
Client (Website / CLI / API)  →  Request  →  Server
Server                        →  Response →  Client
```

- The **client** sends requests (e.g., a database query, API call, or web page request).
- The **server** processes the request and returns a response.
- Example: Request a 1 TB MySQL database with 4 CPUs and 32 GB RAM → receive credentials and query responses.

### Core Characteristics

| Characteristic | Description |
|----------------|-------------|
| **On-demand self-service** | Provision resources without human interaction with the provider. |
| **Pay-as-you-go** | Pay only for what you request or use; return unused resources to stop paying. |
| **Rapid elasticity** | Resources available in seconds or minutes — sometimes instantly. |
| **Broad network access** | Access services over the internet from anywhere. |
| **Resource pooling** | Provider pools resources to serve multiple customers (multi-tenancy). |
| **Measured service** | Usage is monitored, controlled, and reported (metering). |

---

## Traditional IT vs Cloud Computing

### Traditional IT — What You Manage

When provisioning traditional IT infrastructure (e.g., requesting three servers), you must handle:

| Area | Responsibilities |
|------|-----------------|
| **Hardware** | Servers, computers, networking equipment |
| **Facilities** | Power, cooling, physical space |
| **Networking** | Internet access, cabling, firewalls |
| **Storage** | SAN, NAS, local disks |
| **Security** | Physical security, access control |
| **Software** | OS installation, applications, databases |
| **Operations** | Migrations, upgrades, patches |
| **Governance** | Compliance, auditing, policy |

**Typical provisioning timeline:** 3–6 weeks (or at best, 3 days) from request to usable server.

### Traditional IT — Pros and Cons

| Pros | Cons |
|------|------|
| Improved security (full control) | Increased costs / poor ROI |
| Greater customization | Limited scalability |
| More control over infrastructure | Responsible for everything |
| | Limited geographic locations |
| | More personnel required |
| | Long provisioning times |

### What Cloud Computing Offloads

Cloud providers take responsibility for:

- **Internet access & networking**
- **Physical security**
- **Power & cooling**
- **Hardware maintenance**
- **Scaling, abstraction, and high availability**
- **Data migration tooling**

You retain responsibility for configuring and securing your applications and data (see **Shared Responsibility Model** in the glossary).

### AWS vs Traditional IT — The Shift

| Traditional IT | AWS / Cloud |
|----------------|-------------|
| Order hardware, power cables, cooling, rack space | Provision a **service** (e.g., EC2 instance) that includes networking and power |
| Manage physical objects | Configure **virtual services** through a console, CLI, or API |
| Weeks to months to provision | Seconds to minutes to provision |
| Large upfront capital expense (CAPEX) | Variable operational expense (OPEX) |

---

## Cloud Deployment Models

### Overview

| Model | Description |
|-------|-------------|
| **Cloud (All-in-Cloud)** | Everything runs in the cloud |
| **On-Premises** | Nothing (or minimal) in the cloud |
| **Hybrid** | Mix of cloud and on-premises resources |

### Cloud (All-in-Cloud)

- Common among startups and businesses founded after ~2011.
- Runs all workloads in the cloud.
- Migrates existing projects to the cloud; all new projects are cloud-native.
- Uses the **Shared Responsibility Model** for security and operations.

### On-Premises

- Minimal or no cloud usage.
- All projects run in an owned or rented data center.
- Organization is fully responsible for security and operations.
- Typical for legacy companies or organizations requiring strict control over the entire stack.

### Hybrid

- Some application components run in the cloud; others remain on-premises.
- Existing applications are partially migrated; legacy systems may stay on-prem.
- New applications are typically designed for the cloud.
- Requires a fast, reliable connection between on-premises and cloud resources.

---

## Amazon Web Services (AWS) Overview

### What Is AWS?

**Amazon Web Services (AWS)** is a comprehensive, broadly adopted cloud platform offering 300+ services across compute, storage, networking, databases, security, and more.

| Fact | Detail |
|------|--------|
| **First large-scale cloud provider** | AWS pioneered public cloud at scale |
| **Launch year** | 2006 — **Amazon S3** was the first service |
| **Service count** | 300+ services and growing |
| **Pricing model** | Signing up is free; services are generally **pay-to-use** |
| **Market position** | One of the largest cloud communities and fastest-growing providers |
| **Global reach** | Infrastructure available in **31+ regions** worldwide |

---

## AWS Core Service Categories

| Category | Purpose | Example Services |
|----------|---------|-----------------|
| **Compute** | Virtual servers, containers, serverless | EC2, Lambda, ECS, EKS |
| **Networking & Content Delivery** | Connectivity, DNS, CDN | VPC, Route 53, CloudFront, ELB |
| **Storage** | Object, block, and file storage | S3, EBS, EFS, Glacier |
| **Database** | Managed relational and NoSQL databases | RDS, DynamoDB, Aurora, Redshift |
| **Security, Identity & Compliance** | Authentication, encryption, auditing | IAM, KMS, WAF, Shield, GuardDuty |
| **Management & Governance** | Monitoring, deployment, cost management | CloudWatch, CloudTrail, Config, Systems Manager |
| **Application Integration** | Messaging, event routing, workflows | SQS, SNS, EventBridge, Step Functions |
| **Migration & Transfer** | Move workloads to AWS | AWS Migration Hub, DMS, Snowball |

---

## Ways to Interact With AWS

| Method | Best For | Description |
|--------|----------|-------------|
| **AWS Management Console** | Learning, visual confirmation | Web-based GUI for creating and managing resources |
| **AWS CLI** | Engineers, automation, scripting | Command-line tool (`aws` commands) for all AWS services |
| **AWS SDK** | Developers | Language-specific libraries (Python/boto3, JavaScript, Java, etc.) for programmatic access |

### AWS CLI Examples

```bash
aws ec2 describe-instances
aws ec2 start-instance --instance-ids i-1348636c
aws sns publish --topic-arn arn:aws:sns:us-east-1:546419318123:OperationsError --message "Script Failure"
aws sqs receive-message --queue-url https://queue.amazonaws.com/546419318123/Test
```

---

## Benefits of Cloud Computing

### 1. Trade Upfront Expense for Variable Expense

| CAPEX (Capital Expenditure) | OPEX (Operational Expenditure) |
|-----------------------------|--------------------------------|
| Large upfront investment in hardware before use | Pay for usage and requests as you go |
| Fixed costs regardless of utilization | Return unused resources to stop paying |

### 2. Stop Focusing on Data Centers

- **Before:** Invest time and money maintaining data center facilities.
- **After:** Focus on **customers and applications** instead of infrastructure.

### 3. Stop Guessing Capacity

- **Before:** Bound by hardware limits and vendor supply; over-provision to avoid outages.
- **After:** Scale in and out as needed; experiment with load and performance without hardware constraints.

### 4. Benefit From Massive Economies of Scale

- **Smaller scale:** Pay higher per-unit prices based only on your usage.
- **Cloud scale:** Benefit from aggregated usage across millions of customers, driving per-unit price reductions.

### 5. Increase Speed and Business Agility

| Data Center Requests | Cloud Requests |
|---------------------|----------------|
| Days, weeks, or months | Seconds or minutes |

### 6. Go Global in Minutes

- **On-premises:** Limited to locations where you have data centers.
- **AWS:** Deploy globally across 31+ regions with a few clicks or API calls.

---

## AWS Economic & Pricing Models

### Overview

| Model | Description |
|-------|-------------|
| **Free Tier** | Certain services are always free; others are free for 12 months after account creation |
| **On-Demand** | Full pay-as-you-go pricing with no contract — maximum flexibility |
| **Reservations** | 1- or 3-year contracts for discounted rates on predictable workloads |
| **Volume Discounts** | Pay less per unit as usage increases |
| **Price Drops** | Periodic AWS price reductions across services (129+ price drops from 2006–2023) |

### Free Tier

- Always-free services (e.g., limited Lambda invocations, DynamoDB capacity).
- 12-month free tier for new accounts on select services (e.g., EC2 t2.micro, S3 storage limits).

### On-Demand

- No upfront payment or long-term commitment.
- Billed per second (EC2) or per request/GB (S3, Lambda).
- Ideal for unpredictable, spiky, or short-term workloads.

**Example:** 2 processors, 16 GB RAM, running for 10 hours = pay only for those 10 hours.

### Reservations

- Commit to 1 or 3 years for significant discounts (up to ~72% vs on-demand for EC2).
- Types: **Standard** (fixed instance), **Convertible** (change instance family), **Scheduled** (specific time windows).

### Volume Discounts

Usage tiers reduce the per-unit cost as volume grows.

**Example — S3 Standard storage pricing tiers:**
- First 50 TB/month — lowest tier rate
- Next 450 TB/month — reduced rate
- Over 500 TB/month — further reduced rate

### Price Drops

AWS periodically lowers prices as infrastructure costs decrease.

**Example — S3 in us-east-1:**
- 2006: ~$0.15 per GB
- 2023: ~$0.023–$0.026 per GB

---

## Cloud Design Principles

Cloud-native design on AWS follows four foundational principles. A deeper framework — the **AWS Well-Architected Framework** — expands on these at the architect level.

### 1. Design for Failure

> *"Everything fails all the time."* — Werner Vogels, AWS CTO

- Identify **single points of failure** and add redundancy.
- Plan for **resiliency and auto-recovery** when components fail.
- Be intentional about failure scenarios rather than assuming uptime.

### 2. Decouple Components

> *"Watch for coupling that is too tight."* — Steve McConnell

- **Tight coupling:** One component failure or traffic surge affects the entire system; risk of data loss.
- **Loose coupling:** Insert queues (e.g., SQS) or scaling layers between components so surges are absorbed without cascading failures.

### 3. Implement Elasticity

> *"The ability to acquire resources as you need them and release resources when you no longer need them. In the cloud, you want to do this automatically."* — AWS Documentation

- Scale out during peak demand; scale in during low demand.
- Achieve better costs and better performance without fixed hardware boundaries.
- Use Auto Scaling groups, serverless (Lambda), and managed services.

### 4. Think Parallel

- **Serial processing:** 1 server completes a job in 36 hours.
- **Parallel processing:** 3 servers complete the same job in 12 hours.
- Distribute work across multiple instances for increased concurrency and throughput.

### AWS Well-Architected Framework

A structured approach to building secure, high-performing, resilient, and efficient infrastructure. Six pillars:

1. **Operational Excellence**
2. **Security**
3. **Reliability**
4. **Performance Efficiency**
5. **Cost Optimization**
6. **Sustainability**

*(Detailed at Solutions Architect level; referenced here for awareness at Cloud Practitioner level.)*

---

## Glossary of Key Terms

| Term | Definition |
|------|------------|
| **ARN** | Amazon Resource Name — globally unique identifier for any AWS resource |
| **Auto Scaling** | Automatically adjusts the number of EC2 instances based on demand |
| **Availability Zone (AZ)** | Isolated data center within an AWS Region |
| **CAPEX** | Capital Expenditure — upfront investment in physical assets |
| **Client-Server Model** | Architecture where clients request services and servers respond |
| **Cloud Computing** | On-demand delivery of IT resources over the internet with pay-as-you-go pricing |
| **Console** | AWS Management Console — web GUI for managing AWS resources |
| **EC2** | Elastic Compute Cloud — resizable virtual servers in AWS |
| **Elasticity** | Ability to automatically acquire and release resources based on demand |
| **Free Tier** | AWS program offering limited free usage on select services |
| **High Availability (HA)** | Design ensuring minimal downtime through redundancy |
| **Hybrid Cloud** | Deployment model combining on-premises and cloud resources |
| **IAM** | Identity and Access Management — controls who can access AWS resources |
| **Loose Coupling** | Architecture where components interact through intermediaries (queues, APIs) minimizing direct dependencies |
| **Multi-Tenancy** | Multiple customers share the same physical infrastructure with logical isolation |
| **OPEX** | Operational Expenditure — ongoing costs for running services |
| **On-Demand Pricing** | Pay-as-you-go with no long-term commitment |
| **On-Premises** | IT infrastructure hosted in an organization's own data center |
| **Pay-as-you-go** | Billing model where you pay only for resources consumed |
| **Region** | Geographic area containing multiple Availability Zones |
| **Reserved Instances** | Discounted pricing in exchange for a 1- or 3-year usage commitment |
| **S3** | Simple Storage Service — scalable object storage |
| **Scalability** | Ability to handle increased load by adding resources |
| **Shared Responsibility Model** | AWS secures the cloud; customers secure what they put in the cloud |
| **Single Point of Failure** | Component whose failure causes the entire system to fail |
| **VPC** | Virtual Private Cloud — isolated network environment in AWS |
| **VPS** | Virtual Private Server — virtualized dedicated server environment |
| **Volume Discount** | Reduced per-unit pricing at higher usage tiers |
| **Well-Architected Framework** | AWS best-practice guide covering six pillars of cloud architecture |

---

## Study Topics (Upcoming)

The Cloud Practitioner exam also covers these domains — to be expanded in future sections:

- **Security** — IAM, encryption, compliance, Shared Responsibility Model
- **Billing & Pricing** — Cost Explorer, Budgets, Support plans
- **Technology & Services** — Deep dive into individual AWS services

---

## References

- [AWS Cloud Practitioner Exam Guide](https://aws.amazon.com/certification/certified-cloud-practitioner/)
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS Free Tier](https://aws.amazon.com/free/)
