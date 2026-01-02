# Domain 1: Cloud Concepts (24%)

Practice questions covering cloud concepts, benefits, design principles, and migration.

---

## Question 1

**Which of the following are advantages of cloud computing? (Select TWO)**

A) Trade capital expense for variable expense
B) Benefit from economies of scale
C) Guess your infrastructure capacity needs
D) Maintain physical servers in your data center
E) Increase time to market for new applications

<details>
<summary>Answer</summary>

**Correct Answers: A, B**

**Explanation:**
- **A) Correct** - One of the six advantages: Trade CapEx for OpEx. Pay only for what you use instead of investing in data centers.
- **B) Correct** - Massive economies of scale allow AWS to offer lower prices through aggregated usage.
- **C) Incorrect** - Cloud computing eliminates the need to guess capacity. You can scale based on actual demand.
- **D) Incorrect** - This is the opposite of a cloud advantage. Cloud eliminates the need to maintain physical servers.
- **E) Incorrect** - Cloud computing decreases (not increases) time to market by providing instant infrastructure.

**Key Concept:** Six Advantages of Cloud Computing
</details>

---

## Question 2

**A company wants to deploy an application that can automatically scale based on demand. Which cloud computing characteristic does this describe?**

A) Measured service
B) Rapid elasticity
C) Resource pooling
D) Broad network access

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - Rapid elasticity refers to the ability to scale resources up or down automatically based on demand.
- **A) Incorrect** - Measured service means you pay only for what you use (metered billing).
- **C) Incorrect** - Resource pooling means shared resources across multiple customers.
- **D) Incorrect** - Broad network access means accessing services via console, CLI, APIs, and SDKs.

**Key Concept:** Five Criteria of Cloud Computing
</details>

---

## Question 3

**What is the difference between high availability and fault tolerance?**

A) High availability eliminates all downtime, while fault tolerance allows brief downtime
B) Fault tolerance continues operating through failures, while high availability allows brief downtime during recovery
C) They are the same thing
D) High availability is more expensive than fault tolerance

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - Fault tolerance = zero downtime (continues operating through failure). High availability = quick recovery (brief downtime acceptable).
- **A) Incorrect** - Reversed definitions.
- **C) Incorrect** - They have different requirements and implementations.
- **D) Incorrect** - Actually, fault tolerance is typically more expensive as it requires complete redundancy.

**Key Concept:** Architecture Concepts
</details>

---

## Question 4

**Which deployment model combines on-premises infrastructure with cloud resources?**

A) Public cloud
B) Private cloud
C) Hybrid cloud
D) Multi-cloud

<details>
<summary>Answer</summary>

**Correct Answer: C**

**Explanation:**
- **C) Correct** - Hybrid cloud combines public cloud with private/on-premises infrastructure.
- **A) Incorrect** - Public cloud is fully in AWS/Azure/GCP.
- **B) Incorrect** - Private cloud is dedicated on-premises infrastructure.
- **D) Incorrect** - Multi-cloud uses multiple public cloud providers together.

**Key Concept:** Cloud Deployment Models
</details>

---

## Question 5

**A company wants to migrate to AWS and is evaluating different strategies. Which migration strategy involves making minimal changes to applications before moving them to the cloud?**

A) Refactor
B) Replatform
C) Rehost
D) Retire

<details>
<summary>Answer</summary>

**Correct Answer: C**

**Explanation:**
- **C) Correct** - Rehost (lift and shift) involves moving applications with no changes.
- **B) Incorrect** - Replatform (lift, tinker, and shift) involves minor optimizations.
- **A) Incorrect** - Refactor (re-architect) involves significant code changes to be cloud-native.
- **D) Incorrect** - Retire means decommissioning applications.

**Key Concept:** Seven Rs of Migration
</details>

---

## Question 6

**What does vertical scaling mean?**

A) Adding more instances of the same size
B) Distributing workload across multiple availability zones
C) Increasing the size/capacity of a single instance
D) Using auto scaling groups

<details>
<summary>Answer</summary>

**Correct Answer: C**

**Explanation:**
- **C) Correct** - Vertical scaling (scale up) means using a bigger instance (e.g., t2.micro → t2.large).
- **A) Incorrect** - This describes horizontal scaling (scale out).
- **B) Incorrect** - This describes distribution for high availability.
- **D) Incorrect** - Auto Scaling Groups typically implement horizontal scaling.

**Key Concept:** Scaling Concepts
</details>

---

## Question 7

**Which of the following is NOT one of the six advantages of cloud computing?**

A) Stop guessing capacity
B) Go global in minutes
C) Eliminate all security responsibilities
D) Increase speed and agility

<details>
<summary>Answer</summary>

**Correct Answer: C**

**Explanation:**
- **C) Correct** - This is NOT an advantage. Security is a shared responsibility; customers still have security responsibilities.
- **A, B, D) Incorrect** - These are all legitimate advantages of cloud computing.

**Key Concept:** Six Advantages of Cloud Computing
</details>

---

## Question 8

**A startup wants to launch a new web application but doesn't know how much traffic to expect. What cloud computing benefit best addresses this concern?**

A) Trade CapEx for OpEx
B) Stop guessing capacity
C) Economies of scale
D) Go global in minutes

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - "Stop guessing capacity" means you can scale based on actual demand rather than predicting capacity needs.
- **A) Incorrect** - While beneficial, this addresses cost structure, not capacity uncertainty.
- **C) Incorrect** - This addresses overall cost reduction through shared resources.
- **D) Incorrect** - This addresses geographic distribution, not capacity planning.

**Key Concept:** Six Advantages of Cloud Computing
</details>

---

## Question 9

**What is the primary goal of disaster recovery?**

A) Prevent all failures from occurring
B) Continue operating during any failure
C) Recover from disasters following a pre-planned process
D) Automatically scale resources during peak demand

<details>
<summary>Answer</summary>

**Correct Answer: C**

**Explanation:**
- **C) Correct** - Disaster recovery is about having a pre-planned process to recover from disasters.
- **A) Incorrect** - No system can prevent all failures.
- **B) Incorrect** - This describes fault tolerance.
- **D) Incorrect** - This describes elasticity/auto scaling.

**Key Concept:** Architecture Concepts
</details>

---

## Question 10

**Which cloud deployment model would AWS Outposts represent?**

A) Public cloud
B) Private cloud
C) Hybrid cloud
D) Community cloud

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - AWS Outposts brings AWS infrastructure to your on-premises data center, representing a private cloud deployment.
- **A) Incorrect** - Public cloud is hosted entirely by the cloud provider.
- **C) Incorrect** - While Outposts can be part of a hybrid setup, Outposts itself is private cloud infrastructure.
- **D) Incorrect** - Community cloud is shared among specific organizations.

**Key Concept:** Cloud Deployment Models, AWS Outposts
</details>

---

## Question 11

**What does elasticity mean in cloud computing?**

A) Physical properties of data center hardware
B) Ability to manually adjust capacity
C) Automatic horizontal scaling based on demand
D) Ability to handle increasing workload by adding resources

<details>
<summary>Answer</summary>

**Correct Answer: C**

**Explanation:**
- **C) Correct** - Elasticity specifically refers to automatic horizontal scaling based on demand.
- **A) Incorrect** - Elasticity is a software/capacity concept, not physical hardware.
- **B) Incorrect** - Elasticity is automatic, not manual.
- **D) Incorrect** - This describes general scalability, not the automatic nature of elasticity.

**Key Concept:** Elasticity vs Scalability
</details>

---

## Question 12

**A company is planning to migrate its applications to AWS. Which of the following represents the "Replatform" strategy?**

A) Moving applications without any changes
B) Making minor optimizations during migration
C) Completely redesigning the application for cloud
D) Switching to a SaaS solution

<details>
<summary>Answer</summary>

**Correct Answer: B**

**Explanation:**
- **B) Correct** - Replatform (lift, tinker, and shift) involves making minor optimizations during migration.
- **A) Incorrect** - This describes Rehost (lift and shift).
- **C) Incorrect** - This describes Refactor (re-architect).
- **D) Incorrect** - This describes Repurchase (drop and shop).

**Key Concept:** Seven Rs of Migration
</details>

---

## Summary

**Key Topics Covered:**
- Six advantages of cloud computing
- Five criteria of cloud computing
- Architecture concepts (HA, FT, DR)
- Scaling concepts (vertical, horizontal, elasticity)
- Cloud deployment models
- Seven Rs of migration

**Study Tips:**
- Memorize the six advantages and five criteria
- Understand the difference between HA, FT, and DR
- Know when to use each migration strategy
- Distinguish between vertical and horizontal scaling

**Common Mistakes:**
- Confusing high availability with fault tolerance
- Mixing up the seven Rs of migration
- Not understanding elasticity vs manual scaling
