# AWS Cloud Fundamentals

A comprehensive summary of AWS Cloud Practitioner (CLF-C02) course content.

---

## Table of Contents

1. [Cloud Concepts](#1-cloud-concepts)
2. [Security and Compliance](#2-security-and-compliance)
3. [Global Infrastructure](#3-global-infrastructure)
4. [Compute Services](#4-compute-services)
5. [Networking](#5-networking)
6. [Storage Services](#6-storage-services)
7. [Database Services](#7-database-services)
8. [AI/ML and Analytics](#8-aiml-and-analytics)
9. [Security Services](#9-security-services)
10. [Monitoring and Governance](#10-monitoring-and-governance)
11. [Pricing and Support](#11-pricing-and-support)
12. [Migration](#12-migration)
13. [Well-Architected Framework](#13-well-architected-framework)

---

## 1. Cloud Concepts

### Five Criteria of Cloud Computing

| Criteria | Description |
|----------|-------------|
| On-demand self-service | Provision resources without human intervention |
| Broad network access | Access via console, CLI, APIs, SDKs |
| Resource pooling | Shared resources across customers (economies of scale) |
| Rapid elasticity | Scale up/down based on demand |
| Measured service | Pay only for what you use |

### Six Advantages of Cloud Computing

1. **Trade CapEx for OpEx** - No upfront investment, pay as you go
2. **Massive economies of scale** - Lower costs through aggregated usage
3. **Stop guessing capacity** - Scale based on actual demand
4. **Increase speed and agility** - Deploy resources in minutes
5. **Stop running data centers** - Focus on business, not infrastructure
6. **Go global in minutes** - Deploy worldwide with a few clicks

### Key Architecture Concepts

| Concept | Description |
|---------|-------------|
| **High Availability** | Quick recovery from failure (brief downtime acceptable) |
| **Fault Tolerance** | Continue operating through failure (zero downtime) |
| **Disaster Recovery** | Pre-planned process to recover from disasters |
| **Vertical Scaling** | Scale up - bigger instance (t2.micro → t2.large) |
| **Horizontal Scaling** | Scale out - more instances (1 → 3 instances) |
| **Elasticity** | Automatic horizontal scaling based on demand |

### Cloud Deployment Models

| Model | Description |
|-------|-------------|
| **Public Cloud** | AWS, Azure, GCP - all cloud criteria met |
| **Private Cloud** | Dedicated on-premises (AWS Outposts) |
| **Hybrid Cloud** | Public + Private cloud together |
| **Multi-Cloud** | Multiple public clouds together |

---

## 2. Security and Compliance

### Shared Responsibility Model

**AWS Responsibility - Security OF the Cloud:**
- Physical data centers
- Hardware and networking
- Hypervisor
- Managed service infrastructure

**Customer Responsibility - Security IN the Cloud:**
- Customer data
- Platform, applications, IAM
- Operating system (on EC2)
- Firewall/network configuration
- Encryption

### Responsibility by Service Type

| Service Type | Customer Responsibility |
|--------------|------------------------|
| **IaaS (EC2)** | OS patching, security groups, data |
| **PaaS (Elastic Beanstalk)** | Application code, data |
| **SaaS/Managed (RDS, Lambda)** | Data, access management |

### Authentication vs Authorization

- **Authentication**: Verifying identity (username/password, MFA)
- **Authorization**: Determining what actions a user can perform (permissions)

---

## 3. Global Infrastructure

### Hierarchy

```
Edge Locations (400+) → Regions (30+) → Availability Zones (90+)
```

| Component | Description | Use Case |
|-----------|-------------|----------|
| **Region** | Geographic area with 2+ AZs | Data residency, compliance |
| **Availability Zone** | 1+ isolated data centers | High availability |
| **Edge Location** | CloudFront cache points | Low latency content delivery |
| **Local Zone** | Extension close to users | Ultra-low latency |
| **Wavelength Zone** | 5G network edge | Mobile app latency |

### Service Resilience Levels

| Level | Description | Examples |
|-------|-------------|----------|
| **Global** | Survives region failure | IAM, Route 53, CloudFront |
| **Regional** | Survives AZ failure | S3, DynamoDB, EFS |
| **Zonal** | Single AZ | EC2, EBS |

---

## 4. Compute Services

| Service | Type | Use Case |
|---------|------|----------|
| **EC2** | Virtual servers (IaaS) | Full control, any workload |
| **Lambda** | Serverless functions (FaaS) | Event-driven, short tasks |
| **Elastic Beanstalk** | PaaS | Deploy apps without managing infra |
| **ECS** | Container orchestration | Docker containers |
| **EKS** | Kubernetes | Kubernetes workloads |
| **Fargate** | Serverless containers | Containers without servers |
| **Lightsail** | Simple VPS | Beginners, simple apps |
| **AWS Batch** | Batch processing | Large-scale batch jobs |

### EC2 Instance Categories

| Category | Use Case |
|----------|----------|
| General Purpose | Default, balanced workloads |
| Compute Optimized | HPC, ML, gaming |
| Memory Optimized | In-memory databases |
| Storage Optimized | Data warehousing |
| Accelerated | GPU, FPGA workloads |

### Auto Scaling & Load Balancing

| Component | Purpose |
|-----------|---------|
| **Auto Scaling Groups** | Automatically adjust EC2 capacity |
| **Application Load Balancer (ALB)** | HTTP/HTTPS (Layer 7) |
| **Network Load Balancer (NLB)** | TCP/UDP (Layer 4) |
| **Gateway Load Balancer** | Third-party appliances |

---

## 5. Networking

### VPC Components

| Component | Function |
|-----------|----------|
| **VPC** | Virtual private network in AWS |
| **Subnet** | Network segment in one AZ |
| **Internet Gateway** | Connect VPC to internet |
| **NAT Gateway** | Outbound internet for private subnets |
| **Route Table** | Traffic routing rules |
| **VPC Peering** | Connect two VPCs |
| **VPC Endpoints** | Private access to AWS services |
| **PrivateLink** | Private service connections |

### Connectivity Options

| Option | Description |
|--------|-------------|
| **Public Internet** | Standard internet connection |
| **VPN** | Encrypted tunnel over internet |
| **Direct Connect** | Dedicated private connection (physical fiber) |

### Network Security

| Component | Level | State | Explicit Deny |
|-----------|-------|-------|---------------|
| **Security Groups** | Instance (ENI) | Stateful | No (allow only) |
| **Network ACLs** | Subnet | Stateless | Yes |
| **AWS WAF** | Application (Layer 7) | N/A | Yes |

### Edge Services

| Service | Purpose |
|---------|---------|
| **CloudFront** | CDN - caching at edge locations |
| **Global Accelerator** | TCP/UDP acceleration, static IPs |
| **Route 53** | DNS service, domain registration |

---

## 6. Storage Services

### Storage Types Comparison

| Feature | S3 | EBS | EFS |
|---------|----|----|-----|
| **Type** | Object | Block | File |
| **Access** | HTTP/API | Single EC2 | Multiple EC2 |
| **Durability** | 11 9s | Per AZ | Regional |
| **Boot Volume** | No | Yes | No |

### S3 Storage Classes

| Class | Access Pattern | Retrieval | Use Case |
|-------|----------------|-----------|----------|
| **Standard** | Frequent | Immediate | Active data |
| **Intelligent-Tiering** | Variable | Automatic | Unknown patterns |
| **Standard-IA** | Infrequent | Immediate | Backups |
| **One Zone-IA** | Infrequent | Immediate | Reproducible data |
| **Glacier Instant** | Archive | Milliseconds | Archive with fast access |
| **Glacier Flexible** | Archive | Minutes-hours | Long-term archive |
| **Glacier Deep Archive** | Archive | 12+ hours | Compliance archives |

### Other Storage Services

| Service | Use Case |
|---------|----------|
| **EFS** | Shared file system for Linux |
| **FSx for Windows** | Windows file server (SMB protocol) |
| **FSx for Lustre** | High-performance computing, ML |
| **Storage Gateway** | Hybrid storage (on-prem to cloud) |
| **AWS Backup** | Centralized backup service |
| **Instance Store** | Temporary storage attached to EC2 host |

### S3 Features

| Feature | Purpose |
|---------|---------|
| **Versioning** | Prevent accidental deletion |
| **Lifecycle Policies** | Automatically move data between tiers |
| **Encryption** | Server-side encryption by default |

---

## 7. Database Services

### Database Types

| Service | Type | Use Case |
|---------|------|----------|
| **RDS** | Managed relational | MySQL, PostgreSQL, Oracle, SQL Server |
| **Aurora** | AWS-optimized relational | High performance MySQL/PostgreSQL |
| **DynamoDB** | NoSQL key-value | Serverless, millisecond latency |
| **ElastiCache** | In-memory cache | Redis, Memcached |
| **Redshift** | Data warehouse | OLAP, analytics, petabyte-scale |
| **Neptune** | Graph database | Social networks, recommendations |
| **DocumentDB** | Document database | MongoDB compatible |
| **MemoryDB** | In-memory (Redis) | Durable in-memory |

### Database Concepts

| Concept | Description |
|---------|-------------|
| **Multi-AZ** | Synchronous replication for high availability |
| **Read Replica** | Asynchronous replication for read scaling |
| **Aurora Serverless** | Auto-scaling Aurora |
| **DAX** | DynamoDB caching (microsecond latency) |

### Database Migration

| Tool | Purpose |
|------|---------|
| **DMS** | Database Migration Service |
| **SCT** | Schema Conversion Tool (heterogeneous migrations) |

---

## 8. AI/ML and Analytics

### AI/ML Services

| Service | Function |
|---------|----------|
| **SageMaker** | Build, train, deploy ML models |
| **Amazon Bedrock** | Foundation models for generative AI |
| **Amazon Q** | AI assistant for business |
| **Rekognition** | Image and video analysis |
| **Lex** | Chatbots (voice/text) |
| **Polly** | Text-to-speech |
| **Transcribe** | Speech-to-text |
| **Translate** | Language translation |
| **Comprehend** | NLP, sentiment analysis |
| **Textract** | Extract text from documents |
| **Kendra** | Intelligent search |

### Analytics Services

| Service | Function |
|---------|----------|
| **Athena** | Serverless SQL queries on S3 |
| **Kinesis** | Real-time streaming data |
| **EMR** | Big data (Hadoop/Spark) |
| **Glue** | ETL (extract, transform, load) |
| **QuickSight** | Business intelligence dashboards |
| **Redshift** | Data warehousing |
| **OpenSearch** | Search and analytics |

---

## 9. Security Services

### Identity and Access Management (IAM)

| Component | Description |
|-----------|-------------|
| **Users** | Individual identities with credentials |
| **Groups** | Collection of users |
| **Roles** | Temporary credentials (assumed by users/services) |
| **Policies** | JSON permission documents |

### IAM Best Practices

- **Principle of Least Privilege**: Only minimum required permissions
- **MFA**: Enable multi-factor authentication
- **Root User**: Never use for daily tasks, enable MFA immediately
- **IAM Identity Center**: SSO for multiple accounts

### Root User Only Tasks

- Change account settings
- Close AWS account
- Change/cancel support plan
- Enable MFA on S3 bucket delete

### Security Services

| Service | Function |
|---------|----------|
| **Shield** | DDoS protection (Standard free, Advanced paid) |
| **WAF** | Web application firewall (SQL injection, XSS) |
| **GuardDuty** | Threat detection (ML-based) |
| **Inspector** | Vulnerability assessment |
| **Macie** | Sensitive data discovery (PII in S3) |
| **Detective** | Investigate security findings |
| **Security Hub** | Centralized security view |

### Encryption Services

| Service | Function |
|---------|----------|
| **KMS** | Key management and encryption |
| **CloudHSM** | Hardware security modules |
| **Secrets Manager** | Store secrets (API keys, passwords) |
| **Certificate Manager (ACM)** | SSL/TLS certificates |

### Data Encryption Types

| Type | Description |
|------|-------------|
| **At Rest** | Data stored (S3, EBS, RDS) |
| **In Transit** | Data moving (SSL/TLS, HTTPS) |

---

## 10. Monitoring and Governance

### Monitoring Services

| Service | Function |
|---------|----------|
| **CloudWatch** | Metrics, logs, alarms, dashboards |
| **CloudTrail** | API audit trail (who did what, when) |
| **X-Ray** | Distributed tracing, debug applications |

### CloudWatch Features

| Feature | Description |
|---------|-------------|
| **Metrics** | Collect data from AWS resources |
| **Alarms** | Set thresholds, trigger notifications |
| **Dashboards** | Visualize metrics in real-time |
| **Logs** | Centralized log management |

### Compliance and Governance

| Service | Function |
|---------|----------|
| **AWS Artifact** | Access compliance reports (SOC, PCI, HIPAA) |
| **AWS Config** | Track resource configurations |
| **Audit Manager** | Automate evidence collection for audits |
| **Organizations** | Centralized account management |
| **Control Tower** | Multi-account governance with guardrails |
| **Service Catalog** | Manage approved AWS resources |
| **License Manager** | Manage software licenses |

### AWS Organizations

| Feature | Benefit |
|---------|---------|
| **Consolidated Billing** | Single bill, volume discounts |
| **Service Control Policies (SCPs)** | Centralized permissions |
| **Organizational Units (OUs)** | Group accounts hierarchically |

### Health and Recommendations

| Service | Function |
|---------|----------|
| **AWS Health Dashboard** | Service health status, notifications |
| **Trusted Advisor** | Best practice recommendations |
| **IAM Access Analyzer** | Verify least privilege permissions |

### Trusted Advisor Categories

1. Cost Optimization
2. Performance
3. Security
4. Fault Tolerance
5. Service Limits

---

## 11. Pricing and Support

### Key Pricing Concepts

1. **Pay as you go** - No upfront costs, pay for what you use
2. **Save when you commit** - Discounts for 1-3 year commitments
3. **Pay less by using more** - Volume-based discounts

### Cost Drivers

| Factor | Description |
|--------|-------------|
| **Compute** | Processing power and time |
| **Storage** | Amount of data stored |
| **Outbound Data Transfer** | Data leaving AWS |

### EC2 Pricing Models

| Model | Discount | Commitment | Best For |
|-------|----------|------------|----------|
| **On-Demand** | None | None | Unpredictable, short-term |
| **Reserved** | Up to 72% | 1-3 years | Steady-state workloads |
| **Spot** | Up to 90% | None (can be interrupted) | Fault-tolerant, flexible |
| **Savings Plans** | Up to 72% | $/hour commitment | Flexible compute |
| **Dedicated Hosts** | Varies | Physical server | Licensing, compliance |

### Data Transfer Costs

| Transfer | Cost |
|----------|------|
| Data IN | Free |
| Data OUT to internet | Charged |
| Between Regions | Charged |
| Same Region (same AZ) | Free |
| Same Region (different AZ) | Charged |

### Cost Management Tools

| Tool | Purpose |
|------|---------|
| **Cost Explorer** | Visualize and analyze costs |
| **Budgets** | Set spending alerts and thresholds |
| **Cost and Usage Report** | Detailed granular cost data |
| **Pricing Calculator** | Estimate costs before deploying |
| **Cost Allocation Tags** | Track costs by project/team |

### AWS Support Plans (Current 2026)

| Plan | Minimum | Recommended For |
|------|---------|-----------------|
| **Business Support+** | $29/mo | Production workloads (minimum recommended by AWS) |
| **Enterprise Support** | $5k/mo | Business-critical workloads with expert guidance |
| **Unified Operations** | $50k/mo | Mission-critical workloads requiring enhanced resilience |

### Response Times

| Severity | Business Support+ | Enterprise Support | Unified Operations |
|----------|-------------------|-------------------|-------------------|
| Business/Mission-critical down | < 30 min | < 15 min | < 5 min (Incident Mgmt Engineer) |
| Production system down | < 1 hour | < 1 hour | < 1 hour |
| Production system impaired | < 4 hours | < 4 hours | < 4 hours |
| System impaired | < 12 hours | < 12 hours | < 12 hours |
| General guidance | < 24 hours | < 24 hours | < 24 hours |

### Support Plan Features Comparison

| Feature | Business+ | Enterprise | Unified Ops |
|---------|-----------|------------|-------------|
| **AI-powered troubleshooting** | Unlimited 24/7 | Unlimited 24/7 | Unlimited 24/7 |
| **24/7 phone, web, chat, email** | Yes | Yes | Yes |
| **AWS Support App in Slack** | Yes | Yes | Yes |
| **Unlimited cases/contacts** | Yes | Yes | Yes |
| **Third-party software support** | Yes | Yes | Yes |
| **AWS Trusted Advisor** | Full set | Full + Priority | Full + Priority |
| **AWS Health Dashboard & API** | Yes | Yes | Yes |
| **Designated TAM** | No | Yes | Yes |
| **Domain Specialist Engineers** | No | Yes | Yes |
| **Incident Management Engineers** | No | No | Yes |
| **24/7 workload monitoring** | No | No | Yes |
| **White-glove billing concierge** | No | No | Yes |
| **Well-Architected Reviews** | No | Yes | Yes |
| **Proactive security review** | No | Yes | Yes |
| **Continuous architectural reviews** | No | No | Yes |
| **AWS re:Post prioritized responses** | Yes | Yes | Yes |

### Support Plans Pricing Details

**Business Support+** – Greater of **$29/month per account** OR:
- 9% of monthly AWS charges up to $10K
- 7% from $10K to $80K
- 5% from $80K to $250K
- 3% over $250K

**Enterprise Support** – Greater of **$5,000/month** OR:
- 10% of monthly AWS charges up to $150K
- 7% from $150K to $500K
- 5% from $500K to $1M
- 3% over $1M

**Unified Operations** – Greater of **$50,000/month** OR:
- 10% of monthly AWS charges up to $1M
- 6% from $1M to $5M
- 5% over $5M

### Additional Services (Extra Fee)

| Service | Business+ | Enterprise | Unified Ops |
|---------|-----------|------------|-------------|
| AWS Security Incident Response | Available | Available | Available |
| AWS Countdown Premium | Available | Available | Available |
| AWS Incident Detection & Response | No | Available | Available |
| AWS Managed Services | No | Available | Available |

### Support Resources

| Resource | Purpose |
|----------|---------|
| **AWS re:Post** | Community Q&A with prioritized responses on paid plans |
| **AWS Knowledge Center** | FAQs and troubleshooting guides |
| **AWS Marketplace** | Third-party software and integrations |
| **AWS IQ** | On-demand AWS-certified experts |
| **Professional Services** | Project-based consulting |
| **AWS Managed Services** | Ongoing operational management (additional fee) |

---

## 12. Migration

### Three Phases of Migration

| Phase | Description | Key Services |
|-------|-------------|--------------|
| **Assess** | Build business case, assess readiness | Migration Evaluator |
| **Mobilize** | Prepare organization, plan migration | Application Discovery Service, Migration Hub |
| **Migrate & Modernize** | Execute migration | Application Migration Service, DMS, DataSync, Snow Family |

### AWS Cloud Adoption Framework (CAF) - Six Perspectives

| Perspective | Focus | Key Roles |
|-------------|-------|-----------|
| **Business** | Align IT with business outcomes | Business/Finance managers |
| **People** | HR, staffing, training | HR, People managers |
| **Governance** | Minimize risk, maximize value | CIO, Program managers |
| **Platform** | Architecture and infrastructure | CTO, Solutions architects |
| **Security** | Security and compliance | CISO, Security analysts |
| **Operations** | Day-to-day operations | IT operations managers |

### Seven Rs of Migration

| Strategy | Description | Use Case |
|----------|-------------|----------|
| **Retire** | Decommission | No longer needed |
| **Retain** | Keep in source | Not ready to migrate |
| **Rehost** | Lift and shift | Quick migration, no changes |
| **Relocate** | Move VMs/containers | Large-scale migration |
| **Repurchase** | Drop and shop | Switch to SaaS |
| **Replatform** | Lift, tinker, shift | Minor optimizations |
| **Refactor** | Re-architect | Full cloud-native |

### Migration Services

| Service | Purpose |
|---------|---------|
| **Migration Evaluator** | Build business case, cost estimates |
| **Application Discovery Service** | Discover on-premises inventory |
| **Migration Hub** | Centralized migration tracking |
| **Application Migration Service** | Migrate applications (lift and shift) |
| **DMS** | Database Migration Service |
| **SCT** | Schema Conversion Tool |
| **DataSync** | Fast online data transfer |
| **Transfer Family** | SFTP, FTPS, FTP to S3 |
| **Direct Connect** | Dedicated network connection |

### Snow Family (Offline Transfer)

| Device | Capacity | Use Case |
|--------|----------|----------|
| **Snowcone** | 8 TB | Portable, edge computing |
| **Snowball Edge** | Terabytes-petabytes | Large data migrations |
| **Snowmobile** | Exabytes | Massive data center moves |

---

## 13. Well-Architected Framework

### Six Pillars

| Pillar | Focus |
|--------|-------|
| **Operational Excellence** | Run and monitor systems, improve processes |
| **Security** | Protect data, systems, and assets |
| **Reliability** | Recover from failures, meet demand |
| **Performance Efficiency** | Use resources efficiently |
| **Cost Optimization** | Avoid unnecessary costs |
| **Sustainability** | Minimize environmental impact |

### Pillar Details

**Operational Excellence:**
- Automate deployments through CI/CD pipelines
- Use infrastructure as code (CloudFormation)
- Implement self-healing mechanisms

**Security:**
- Principle of least privilege
- Encrypt data at rest and in transit
- Enable traceability with logging

**Reliability:**
- Design for failure recovery
- Use multiple AZs
- Implement auto scaling

**Performance Efficiency:**
- Rightsize resources
- Use managed services
- Monitor and optimize

**Cost Optimization:**
- Use Spot Instances, Savings Plans
- Rightsize and turn off unused resources
- Track costs with tags

**Sustainability:**
- Use serverless where appropriate
- Optimize resource utilization
- Reduce energy consumption

### AWS Well-Architected Tool

- Self-service tool to assess workloads
- Generates reports against best practices
- Provides remediation recommendations
- Customizable for specific scenarios

---

## Application Integration

| Service | Function |
|---------|----------|
| **SQS** | Message queuing (decouple components) |
| **SNS** | Pub/sub notifications (fan-out) |
| **EventBridge** | Event bus (serverless events) |
| **Step Functions** | Workflow orchestration |

### SQS Types

| Type | Characteristics |
|------|-----------------|
| **Standard** | At-least-once delivery, best-effort ordering |
| **FIFO** | Exactly-once delivery, strict ordering |

---

## Developer Tools

| Service | Function |
|---------|----------|
| **CodeCommit** | Source control (Git) |
| **CodeBuild** | Build service |
| **CodeDeploy** | Deployment automation |
| **CodePipeline** | CI/CD pipeline |
| **Cloud9** | Cloud IDE |
| **X-Ray** | Distributed tracing |
| **AppSync** | GraphQL APIs |
| **Amplify** | Full-stack application development |

---

## Business Applications

| Service | Function |
|---------|----------|
| **Amazon Connect** | AI-powered contact center |
| **Amazon SES** | Simple Email Service |
| **Amazon WorkSpaces** | Virtual desktops |
| **Amazon AppStream 2.0** | Stream desktop applications |
| **WorkSpaces Web** | Secure browser access |

---

## IoT Services

| Service | Function |
|---------|----------|
| **AWS IoT Core** | Connect and manage IoT devices |

---

## Quick Reference: Common Exam Traps

### Similar Service Pairs

| If you see... | Don't confuse with... |
|---------------|----------------------|
| CloudWatch (metrics/monitoring) | CloudTrail (API audit) |
| Security Group (instance, stateful) | NACL (subnet, stateless) |
| S3 (objects) | EBS (blocks) |
| EFS (Linux files) | FSx (Windows files) |
| Direct Connect (dedicated) | VPN (over internet) |
| Athena (query S3) | Redshift (data warehouse) |
| SNS (pub/sub) | SQS (queue) |
| Shield (DDoS) | WAF (web attacks) |
| GuardDuty (threats) | Inspector (vulnerabilities) |

### Cost Traps

| Question asks for... | Answer is NOT... |
|---------------------|------------------|
| "Lowest cost" | On-Demand, Dedicated |
| "Cannot tolerate interruption" | Spot Instances |
| "Steady state workload" | On-Demand, Spot |
| "Physical server required" | EC2 (shared), Spot |

### Responsibility Traps

| Service | Who patches OS? |
|---------|-----------------|
| EC2 | Customer |
| RDS | AWS |
| Lambda | AWS |
| Elastic Beanstalk | AWS (managed) |

---

## Exam Tips

1. **Read carefully**: Look for keywords like "most cost-effective", "cannot be interrupted", "dedicated"
2. **Eliminate first**: Remove obviously wrong answers
3. **Time management**: ~83 seconds per question, flag and move on
4. **Never leave blank**: No penalty for guessing
5. **Trust your first instinct**: Usually correct
6. **Watch for absolutes**: "Always", "Never", "Guarantees" are usually wrong

---

## Numbers to Remember

- **6** pillars of Well-Architected Framework
- **7** Rs of migration
- **6** perspectives of AWS CAF
- **3** paid support plans (Business+, Enterprise, Unified Operations)
- **700** passing score
- **90** minutes exam time
- **65** questions (50 scored, 15 unscored)
- **11 9s** - S3 durability (99.999999999%)

---

*This document summarizes key concepts from AWS Cloud Practitioner (CLF-C02) course modules 1-13.*
