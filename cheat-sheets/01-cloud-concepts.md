# Cloud Concepts Cheat Sheet

Quick reference for Domain 1: Cloud Concepts

---

## Five Criteria of Cloud Computing

| Criteria | Description |
|----------|-------------|
| **On-demand self-service** | Provision without human intervention |
| **Broad network access** | Console, CLI, APIs, SDKs |
| **Resource pooling** | Shared across customers (economies of scale) |
| **Rapid elasticity** | Scale up/down based on demand |
| **Measured service** | Pay only for what you use |

**Memory Aid:** OBSRM (On-demand, Broad, Shared, Rapid, Measured)

---

## Six Advantages of Cloud Computing

1. **Trade CapEx for OpEx** - No upfront costs
2. **Economies of scale** - Lower prices through shared usage
3. **Stop guessing capacity** - Scale based on actual demand
4. **Speed and agility** - Deploy in minutes
5. **Stop running data centers** - Focus on business
6. **Go global** - Deploy worldwide quickly

**Memory Aid:** CESSGG (CapEx, Economies, Stop guessing, Speed, Stop datacenters, Go global)

---

## Architecture Concepts

| Concept | Downtime | Description |
|---------|----------|-------------|
| **High Availability** | Brief acceptable | Quick recovery from failure |
| **Fault Tolerance** | Zero (none) | Continue through failure |
| **Disaster Recovery** | Planned | Pre-planned recovery process |

**Scaling:**
- **Vertical** = Scale UP (bigger instance: t2.micro → t2.large)
- **Horizontal** = Scale OUT (more instances: 1 → 3)
- **Elasticity** = Automatic horizontal scaling

---

## Cloud Deployment Models

| Model | Description | Example |
|-------|-------------|---------|
| **Public Cloud** | AWS, Azure, GCP | Standard AWS services |
| **Private Cloud** | Dedicated on-premises | AWS Outposts |
| **Hybrid Cloud** | Public + Private | AWS + On-prem |
| **Multi-Cloud** | Multiple public clouds | AWS + Azure + GCP |

---

## Seven Rs of Migration

| R | Description | Use When |
|---|-------------|----------|
| **Retire** | Decommission | Not needed anymore |
| **Retain** | Keep as-is | Not ready to migrate |
| **Rehost** | Lift and shift | Quick migration, no changes |
| **Relocate** | VM/container move | VMware Cloud on AWS |
| **Repurchase** | Drop and shop | Moving to SaaS |
| **Replatform** | Lift, tinker, shift | Minor optimizations |
| **Refactor** | Re-architect | Full cloud-native |

**Memory Aid:** 3R-Re (Retire, Retain, Rehost, Relocate, Repurchase, Replatform, Refactor)

**Complexity Order:** Rehost < Replatform < Refactor

---

## Migration Phases

1. **Assess** - Build business case (Migration Evaluator)
2. **Mobilize** - Plan migration (Application Discovery)
3. **Migrate & Modernize** - Execute (Application Migration Service, DMS)

---

## Cloud Adoption Framework (CAF) - Six Perspectives

**Business Side:**
- **Business** - Business/Finance managers
- **People** - HR, People managers
- **Governance** - CIO, Program managers

**Technical Side:**
- **Platform** - CTO, Architects
- **Security** - CISO, Security
- **Operations** - IT Ops managers

**Memory Aid:** BPG-PSO (Business, People, Governance | Platform, Security, Operations)

---

## Well-Architected Framework - Six Pillars

1. **Operational Excellence** - Run and improve systems
2. **Security** - Protect data and systems
3. **Reliability** - Recover from failures, meet demand
4. **Performance Efficiency** - Use resources efficiently
5. **Cost Optimization** - Avoid unnecessary costs
6. **Sustainability** - Minimize environmental impact

**Memory Aid:** OSRPCS or "Oh So Really Perfect Cost Savings"

---

## Key Numbers to Remember

- **5** criteria of cloud computing
- **6** advantages of cloud computing
- **7** Rs of migration
- **6** CAF perspectives
- **6** Well-Architected pillars
- **3** migration phases

---

## Common Exam Scenarios

**"Most cost-effective migration"** → Rehost (lift and shift)

**"Optimize for cloud"** → Refactor

**"Quick migration, minimal changes"** → Rehost

**"Application no longer needed"** → Retire

**"Not ready to migrate yet"** → Retain

**"Minor database optimization"** → Replatform

**"Switch to SaaS"** → Repurchase

---

## Quick Decision Trees

### Scaling Decision
- Need bigger instance? → **Vertical scaling**
- Need more instances? → **Horizontal scaling**
- Need automatic scaling? → **Elasticity** (Auto Scaling)

### Availability Decision
- Brief downtime OK? → **High Availability**
- Zero downtime required? → **Fault Tolerance**
- Recovery from disaster? → **Disaster Recovery**

### Migration Strategy Decision
- No changes needed? → **Rehost**
- Minor tweaks? → **Replatform**
- Complete redesign? → **Refactor**
- Switching vendors? → **Repurchase**
- Don't need it? → **Retire**
- Not ready? → **Retain**

---

## Exam Tips

**Keywords to watch:**
- "Most cost-effective" = Usually simplest solution
- "No changes" = Rehost
- "Cloud-native" = Refactor
- "Cannot tolerate downtime" = Fault Tolerance
- "Temporary failure acceptable" = High Availability

**Common traps:**
- Confusing HA with FT
- Mixing up the 7 Rs
- Not knowing the 6 advantages
- Forgetting sustainability is a pillar
