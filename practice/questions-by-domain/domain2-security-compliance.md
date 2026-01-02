# Domain 2: Security and Compliance (30%)

Practice questions covering the Shared Responsibility Model, AWS security services, IAM, and compliance.

---

## Question 1

**According to the AWS Shared Responsibility Model, which of the following is AWS responsible for?**

A) Patching the operating system on EC2 instances
B) Configuring security groups
C) Physical security of data centers
D) Encrypting data at rest in S3

<details>
<summary>Answer</summary>

**Correct Answer: C**

**Explanation:**
- **C) Correct** - AWS is responsible for security OF the cloud, including physical data centers.
- **A) Incorrect** - Customer responsibility for EC2 (IaaS).
- **B) Incorrect** - Customer configures security groups.
- **D) Incorrect** - Customer decides whether to encrypt their data.

**Key Concept:** Shared Responsibility Model
</details>

---

## Question 2

**Which AWS service would you use to manage access permissions for AWS resources?**

A) AWS CloudTrail
B) AWS IAM
C) AWS Config
D) AWS Shield

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - IAM (Identity and Access Management) manages users, groups, roles, and permissions.
- **A) Incorrect** - CloudTrail logs API calls (audit trail).
- **C) Incorrect** - Config tracks resource configurations.
- **D) Incorrect** - Shield provides DDoS protection.

**Key Concept:** IAM - Identity and Access Management
</details>

---

## Question 3

**What is the principle of least privilege?**

A) Users should have maximum permissions to be productive
B) Users should only have the minimum permissions required to do their job
C) All users should share the same credentials
D) Root user should be used for all administrative tasks

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - Least privilege means granting only the minimum necessary permissions.
- **A) Incorrect** - This violates the principle of least privilege.
- **C) Incorrect** - This is a security risk; users should have individual credentials.
- **D) Incorrect** - Root user should never be used for regular tasks.

**Key Concept:** IAM Best Practices
</details>

---

## Question 4

**Which IAM entity should an EC2 instance use to access other AWS services?**

A) IAM User
B) IAM Group
C) IAM Role
D) Root Account

<details>
<summary>Answer</summary>

**Correct Answer: C**

**Explanation:**
- **C) Correct** - EC2 instances should use IAM roles to access other AWS services securely.
- **A) Incorrect** - IAM users are for people, not services.
- **B) Incorrect** - Groups are collections of users.
- **D) Incorrect** - Never use root account for services.

**Key Concept:** IAM Roles
</details>

---

## Question 5

**Which tasks can ONLY be performed by the AWS root user? (Select TWO)**

A) Create IAM users
B) Close the AWS account
C) Change the AWS Support plan
D) Launch EC2 instances
E) Create S3 buckets

<details>
<summary>Answer</summary>

**Correct Answers: B, C**

**Explanation:**
- **B) Correct** - Only root user can close an AWS account.
- **C) Correct** - Only root user can change or cancel the support plan.
- **A, D, E) Incorrect** - These can be delegated to IAM users with appropriate permissions.

**Key Concept:** Root User Only Tasks
</details>

---

## Question 6

**What is the difference between authentication and authorization?**

A) They are the same thing
B) Authentication verifies identity; authorization determines permissions
C) Authorization verifies identity; authentication determines permissions
D) Authentication is only for root users

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - Authentication = "Who are you?" (username/password, MFA). Authorization = "What can you do?" (permissions).
- **A, C, D) Incorrect** - These misrepresent the concepts.

**Key Concept:** Authentication vs Authorization
</details>

---

## Question 7

**For which service type does the customer have the MOST security responsibilities?**

A) SaaS (e.g., AWS managed services like RDS)
B) PaaS (e.g., Elastic Beanstalk)
C) IaaS (e.g., EC2)
D) All have equal responsibility

<details>
<summary>Answer</summary>

**Correct Answer: C**

**Explanation:**
- **C) Correct** - With IaaS (EC2), customers must patch OS, configure security, manage data, etc.
- **A) Incorrect** - SaaS has the least customer responsibility (only data and access).
- **B) Incorrect** - PaaS has moderate responsibility (application code and data).
- **D) Incorrect** - Responsibility varies by service type.

**Key Concept:** Shared Responsibility by Service Type
</details>

---

## Question 8

**Which AWS service provides DDoS protection?**

A) AWS WAF
B) AWS Shield
C) AWS GuardDuty
D) AWS Inspector

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - AWS Shield provides DDoS protection (Standard is free, Advanced is paid).
- **A) Incorrect** - WAF protects against web application attacks (SQL injection, XSS).
- **C) Incorrect** - GuardDuty provides threat detection.
- **D) Incorrect** - Inspector performs vulnerability assessments.

**Key Concept:** Security Services - Shield
</details>

---

## Question 9

**Which service would you use to detect sensitive data like PII in S3 buckets?**

A) Amazon Macie
B) AWS GuardDuty
C) AWS Inspector
D) AWS Config

<details>
<summary>Answer</summary>

**Correct Answer: A**

**Explanation:**
- **A) Correct** - Amazon Macie discovers and protects sensitive data (PII) in S3.
- **B) Incorrect** - GuardDuty provides general threat detection.
- **C) Incorrect** - Inspector assesses vulnerabilities in EC2 and containers.
- **D) Incorrect** - Config tracks resource configurations.

**Key Concept:** Security Services - Macie
</details>

---

## Question 10

**What should you enable immediately after creating a new AWS account?**

A) CloudTrail logging
B) MFA on the root user
C) Billing alerts
D) All of the above

<details>
<summary>Answer</summary>

**Correct Answer: D**

**Explanation:**
- **D) Correct** - All three are security best practices for new accounts.
- **A) Correct** - CloudTrail provides audit logging.
- **B) Correct** - MFA on root user is critical security measure.
- **C) Correct** - Billing alerts prevent unexpected charges.

**Key Concept:** AWS Account Security Best Practices
</details>

---

## Question 11

**Which AWS service manages encryption keys?**

A) AWS Secrets Manager
B) AWS KMS
C) AWS Certificate Manager
D) AWS CloudHSM

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - AWS KMS (Key Management Service) manages encryption keys.
- **A) Incorrect** - Secrets Manager stores secrets like API keys and passwords.
- **C) Incorrect** - Certificate Manager manages SSL/TLS certificates.
- **D) Incorrect** - CloudHSM provides hardware security modules (more control than KMS).

**Key Concept:** Encryption Services - KMS
</details>

---

## Question 12

**Which compliance reports and certifications can you access through AWS Artifact?**

A) SOC reports
B) PCI DSS reports
C) ISO certifications
D) All of the above

<details>
<summary>Answer</summary>

**Correct Answer: D**

**Explanation:**
- **D) Correct** - AWS Artifact provides access to compliance reports including SOC, PCI, ISO, HIPAA, and others.

**Key Concept:** Compliance - AWS Artifact
</details>

---

## Question 13

**A company needs to ensure their EC2 instances are scanned for vulnerabilities. Which service should they use?**

A) AWS GuardDuty
B) AWS Inspector
C) AWS Macie
D) AWS Shield

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - AWS Inspector performs vulnerability assessments on EC2 instances and container images.
- **A) Incorrect** - GuardDuty provides threat detection, not vulnerability scanning.
- **C) Incorrect** - Macie is for sensitive data discovery in S3.
- **D) Incorrect** - Shield provides DDoS protection.

**Key Concept:** Security Services - Inspector
</details>

---

## Question 14

**What type of encryption protects data while it is being transmitted over a network?**

A) Encryption at rest
B) Encryption in transit
C) Server-side encryption
D) Client-side encryption

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - Encryption in transit protects data moving over networks (using SSL/TLS, HTTPS).
- **A) Incorrect** - Encryption at rest protects stored data.
- **C) Incorrect** - Server-side encryption is a type of encryption at rest.
- **D) Incorrect** - Client-side encryption can apply to both rest and transit.

**Key Concept:** Data Encryption Types
</details>

---

## Question 15

**Which service provides centralized threat detection across your AWS environment?**

A) AWS CloudTrail
B) AWS Config
C) AWS GuardDuty
D) AWS Inspector

<details>
<summary>Answer</summary>

**Correct Answer: C**

**Explanation:**
- **C) Correct** - GuardDuty uses ML to detect threats across AWS accounts and workloads.
- **A) Incorrect** - CloudTrail logs API calls but doesn't analyze threats.
- **B) Incorrect** - Config tracks configurations, not threats.
- **D) Incorrect** - Inspector focuses on vulnerability assessment, not active threat detection.

**Key Concept:** Security Services - GuardDuty
</details>

---

## Question 16

**For an RDS database instance, who is responsible for patching the underlying operating system?**

A) Customer
B) AWS
C) Both customer and AWS
D) Third-party vendor

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - RDS is a managed service; AWS handles OS patching.
- **A) Incorrect** - Customer would patch OS on EC2, not RDS.
- **C, D) Incorrect** - AWS fully manages the OS for RDS.

**Key Concept:** Shared Responsibility Model - Managed Services
</details>

---

## Question 17

**Which AWS service helps protect web applications from common exploits like SQL injection and cross-site scripting?**

A) AWS Shield
B) AWS WAF
C) AWS GuardDuty
D) Security Groups

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - AWS WAF (Web Application Firewall) protects against SQL injection, XSS, and other Layer 7 attacks.
- **A) Incorrect** - Shield protects against DDoS attacks.
- **C) Incorrect** - GuardDuty provides threat detection.
- **D) Incorrect** - Security groups are network firewalls, not web application firewalls.

**Key Concept:** Security Services - WAF
</details>

---

## Question 18

**What is the recommended way to provide temporary access to AWS resources for a mobile application?**

A) Embed AWS credentials in the app
B) Use IAM roles
C) Share root account credentials
D) Create an IAM user for each mobile device

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - Use IAM roles with temporary credentials (via AWS STS and services like Cognito).
- **A) Incorrect** - Never embed credentials in applications.
- **C) Incorrect** - Never share root credentials.
- **D) Incorrect** - Not scalable or secure.

**Key Concept:** IAM Best Practices - Temporary Credentials
</details>

---

## Summary

**Key Topics Covered:**
- Shared Responsibility Model
- IAM components (users, groups, roles, policies)
- IAM best practices and root user tasks
- Security services (Shield, WAF, GuardDuty, Inspector, Macie)
- Encryption (KMS, CloudHSM, at rest, in transit)
- Compliance (AWS Artifact)
- Authentication vs Authorization

**Study Tips:**
- Understand exactly what AWS manages vs. customer responsibility
- Know the difference between security services (when to use each)
- Memorize root user only tasks
- Understand principle of least privilege
- Know when to use IAM roles vs users

**Common Mistakes:**
- Confusing security services (Shield vs WAF vs GuardDuty)
- Not understanding shared responsibility by service type
- Mixing up encryption types and services
- Thinking root user can delegate all tasks
