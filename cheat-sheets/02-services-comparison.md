# AWS Services Comparison Cheat Sheet

Quick reference for commonly confused services

---

## Storage Services

### S3 vs EBS vs EFS

| Feature | S3 | EBS | EFS |
|---------|----|----|-----|
| **Type** | Object storage | Block storage | File storage |
| **Access** | HTTP/API | Single EC2 | Multiple EC2 (Linux) |
| **Use Case** | Static files, backups | Boot volumes, databases | Shared file system |
| **Durability** | 11 9s across AZs | Per AZ only | Regional |
| **Can boot EC2?** | No | Yes | No |
| **Scalability** | Unlimited | Fixed size | Auto-scales |

**Memory Aid:**
- **S3** = Objects (photos, videos, documents)
- **EBS** = Block (hard drive for EC2)
- **EFS** = Files (shared Linux filesystem)

---

## Monitoring & Logging

### CloudWatch vs CloudTrail vs X-Ray

| Service | Purpose | What it Tracks |
|---------|---------|----------------|
| **CloudWatch** | Metrics & monitoring | Performance metrics, logs, alarms |
| **CloudTrail** | API audit trail | Who did what, when (API calls) |
| **X-Ray** | Application tracing | Request flow through distributed apps |

**Memory Aid:**
- **CloudWatch** = WATCH performance
- **CloudTrail** = TRAIL of API calls (audit)
- **X-Ray** = X-RAY into application flow

---

## Security Services

### Shield vs WAF vs GuardDuty vs Inspector vs Macie

| Service | Protection Against | Layer |
|---------|-------------------|-------|
| **Shield** | DDoS attacks | Network (L3/L4) |
| **WAF** | Web exploits (SQL injection, XSS) | Application (L7) |
| **GuardDuty** | Threats (ML-based detection) | Account-wide |
| **Inspector** | Vulnerabilities (CVEs) | EC2, Containers |
| **Macie** | Sensitive data exposure (PII) | S3 |

**When to use:**
- DDoS attack → **Shield**
- SQL injection → **WAF**
- Unusual API calls → **GuardDuty**
- Vulnerable software → **Inspector**
- Find PII in S3 → **Macie**

---

## Network Security

### Security Groups vs NACLs

| Feature | Security Group | Network ACL |
|---------|---------------|-------------|
| **Level** | Instance (ENI) | Subnet |
| **State** | Stateful | Stateless |
| **Rules** | Allow only | Allow AND Deny |
| **Return traffic** | Automatic | Must be explicitly allowed |
| **Evaluation** | All rules | Rules in order |

**Memory Aid:**
- **SG** = Stateful, Instance, Allow only
- **NACL** = Stateless, Subnet, Allow + Deny

---

## Database Services

### RDS vs DynamoDB vs Redshift

| Feature | RDS | DynamoDB | Redshift |
|---------|-----|----------|----------|
| **Type** | Relational (SQL) | NoSQL (key-value) | Data warehouse |
| **Use Case** | OLTP | Serverless apps | OLAP analytics |
| **Scalability** | Vertical (instance size) | Horizontal (automatic) | Petabyte-scale |
| **Latency** | Milliseconds | Single-digit milliseconds | Query-dependent |

**When to use:**
- Traditional database → **RDS**
- Serverless, high-speed → **DynamoDB**
- Analytics, big data → **Redshift**

---

## Connectivity

### VPN vs Direct Connect

| Feature | VPN | Direct Connect |
|---------|-----|----------------|
| **Connection** | Over internet (encrypted) | Dedicated physical fiber |
| **Speed** | Internet-dependent | 1 Gbps - 100 Gbps |
| **Cost** | Lower | Higher |
| **Setup Time** | Minutes | Weeks/months |
| **Security** | IPsec encrypted tunnel | Private (not encrypted by default) |

**When to use:**
- Quick setup, lower cost → **VPN**
- High bandwidth, low latency → **Direct Connect**

---

## Compute Services

### EC2 vs Lambda vs Fargate vs ECS vs EKS

| Service | Type | Management | Use Case |
|---------|------|------------|----------|
| **EC2** | Virtual servers | You manage | Full control |
| **Lambda** | Serverless functions | AWS manages | Event-driven, short tasks |
| **ECS** | Container orchestration | Mixed | Docker containers |
| **EKS** | Kubernetes | Mixed | Kubernetes workloads |
| **Fargate** | Serverless containers | AWS manages | Containers without servers |

**Decision tree:**
- Need full control? → **EC2**
- Function under 15 min? → **Lambda**
- Docker containers? → **ECS** or **Fargate**
- Kubernetes? → **EKS**
- Don't want to manage servers? → **Lambda** or **Fargate**

---

## Content Delivery

### CloudFront vs Global Accelerator

| Feature | CloudFront | Global Accelerator |
|---------|------------|-------------------|
| **Purpose** | CDN (content caching) | TCP/UDP acceleration |
| **Best For** | Static/dynamic content | Non-HTTP protocols |
| **Caching** | Yes | No |
| **IP Addresses** | Changes per edge | Static anycast IPs |

**When to use:**
- Cache website content → **CloudFront**
- Accelerate TCP/UDP apps → **Global Accelerator**
- Need static IPs → **Global Accelerator**

---

## Analytics

### Athena vs Redshift vs EMR

| Service | Purpose | Data Source |
|---------|---------|-------------|
| **Athena** | Serverless SQL queries | S3 |
| **Redshift** | Data warehouse | Loaded data |
| **EMR** | Big data (Hadoop/Spark) | Various |

**When to use:**
- Query S3 data → **Athena**
- Data warehouse → **Redshift**
- Hadoop/Spark workloads → **EMR**

---

## Application Integration

### SQS vs SNS vs EventBridge

| Service | Pattern | Use Case |
|---------|---------|----------|
| **SQS** | Queue (pull) | Decouple components |
| **SNS** | Pub/Sub (push) | Fan-out notifications |
| **EventBridge** | Event bus | Serverless event routing |

**When to use:**
- Decouple applications → **SQS**
- Send to multiple targets → **SNS**
- Event-driven architecture → **EventBridge**

---

## Cost Management

### Cost Explorer vs Budgets vs Cost & Usage Report

| Tool | Purpose | Granularity |
|------|---------|-------------|
| **Cost Explorer** | Visualize and analyze | Daily/monthly |
| **Budgets** | Set alerts | Custom thresholds |
| **Cost & Usage Report** | Detailed data | Hourly |

---

## File Storage

### EFS vs FSx for Windows vs FSx for Lustre

| Feature | EFS | FSx Windows | FSx Lustre |
|---------|-----|-------------|------------|
| **OS** | Linux | Windows | Linux |
| **Protocol** | NFS | SMB | POSIX |
| **Use Case** | Linux shared storage | Windows file server | HPC, ML |

**When to use:**
- Linux file sharing → **EFS**
- Windows file server → **FSx for Windows**
- High-performance computing → **FSx for Lustre**

---

## Load Balancers

### ALB vs NLB vs GLB

| Type | Layer | Protocol | Use Case |
|------|-------|----------|----------|
| **ALB** | Layer 7 | HTTP/HTTPS | Web applications |
| **NLB** | Layer 4 | TCP/UDP | High performance, low latency |
| **GLB** | Layer 3 | IP | Third-party appliances |

---

## Encryption

### KMS vs CloudHSM vs Secrets Manager

| Service | Purpose | Control Level |
|---------|---------|---------------|
| **KMS** | Key management | AWS managed |
| **CloudHSM** | Hardware security modules | Customer managed hardware |
| **Secrets Manager** | Store secrets (passwords, API keys) | AWS managed |

**When to use:**
- Encryption keys → **KMS**
- Need dedicated hardware → **CloudHSM**
- Rotate secrets automatically → **Secrets Manager**

---

## Data Migration

### DMS vs DataSync vs Snow Family

| Service | Purpose | Connection |
|---------|---------|------------|
| **DMS** | Database migration | Online |
| **DataSync** | Data transfer (files) | Online |
| **Snow Family** | Offline data transfer | Physical device |

**When to use:**
- Migrate databases → **DMS**
- Transfer files online → **DataSync**
- Large offline transfer → **Snow Family**

---

## Quick Decision Guide

### Storage Decision
- Objects (files)? → **S3**
- Block (disk)? → **EBS**
- Shared files (Linux)? → **EFS**
- Shared files (Windows)? → **FSx for Windows**

### Compute Decision
- Full control? → **EC2**
- Serverless functions? → **Lambda**
- Containers? → **ECS/EKS/Fargate**

### Database Decision
- Relational (SQL)? → **RDS** or **Aurora**
- NoSQL key-value? → **DynamoDB**
- Analytics? → **Redshift**
- In-memory cache? → **ElastiCache**

### Security Decision
- DDoS? → **Shield**
- Web attacks? → **WAF**
- Threat detection? → **GuardDuty**
- Vulnerabilities? → **Inspector**
- PII in S3? → **Macie**

---

## Exam Tips

**Most commonly confused:**
1. CloudWatch vs CloudTrail
2. S3 vs EBS vs EFS
3. Shield vs WAF vs GuardDuty
4. Security Groups vs NACLs
5. ALB vs NLB
6. RDS vs DynamoDB vs Redshift

**Remember:**
- **Stateful** = return traffic automatic (Security Groups)
- **Stateless** = must allow return traffic (NACLs)
- **Object** = files/documents (S3)
- **Block** = hard drive (EBS)
- **Serverless** = no server management (Lambda, Fargate, DynamoDB)
