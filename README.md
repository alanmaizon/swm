# AWS Cloud Practitioner (CLF-C02) Exam Preparation

> Complete study resource for AWS Certified Cloud Practitioner exam preparation

[![AWS Certification](https://img.shields.io/badge/AWS-Cloud%20Practitioner-orange)](https://aws.amazon.com/certification/certified-cloud-practitioner/)
[![Exam](https://img.shields.io/badge/Exam-CLF--C02-blue)](https://aws.amazon.com/certification/certified-cloud-practitioner/)

---

## Overview

This repository contains comprehensive study materials, practice questions, cheat sheets, and tools to help you prepare for the AWS Certified Cloud Practitioner (CLF-C02) exam.

### Exam Details

- **Exam Code**: CLF-C02
- **Duration**: 90 minutes
- **Questions**: 65 (50 scored, 15 unscored)
- **Passing Score**: 700/1000
- **Question Format**: Multiple choice and multiple response
- **Cost**: $100 USD
- **Validity**: 3 years

---

## Repository Structure

```
swm/
├── README.md                          # This file
├── CLAUDE.md                          # AI assistant development guide
├── STUDY-TRACKER.md                   # Personal study progress tracker
├── docs/
│   └── AWS-Cloud-Fundamentals.md     # Comprehensive study guide
├── practice/
│   ├── questions-by-domain/          # Practice questions organized by exam domain
│   └── mock-exams/                   # Full-length mock exams
├── cheat-sheets/                      # Quick reference materials
└── tools/                             # Study utilities and scripts
```

---

## Exam Domains

The CLF-C02 exam covers four main domains:

| Domain | Weight |
|--------|--------|
| **Domain 1**: Cloud Concepts | 24% |
| **Domain 2**: Security and Compliance | 30% |
| **Domain 3**: Cloud Technology and Services | 34% |
| **Domain 4**: Billing, Pricing, and Support | 12% |

---

## Study Plan

### Recommended 4-Week Study Schedule

#### Week 1: Foundations
- [ ] Read [AWS Cloud Fundamentals](docs/AWS-Cloud-Fundamentals.md) - Sections 1-3
  - Cloud Concepts
  - Security and Compliance
  - Global Infrastructure
- [ ] Review [Cloud Concepts Cheat Sheet](cheat-sheets/01-cloud-concepts.md)
- [ ] Complete Domain 1 practice questions
- [ ] Watch AWS Cloud Practitioner Essentials (free course)

#### Week 2: Core Services
- [ ] Read [AWS Cloud Fundamentals](docs/AWS-Cloud-Fundamentals.md) - Sections 4-7
  - Compute Services
  - Networking
  - Storage Services
  - Database Services
- [ ] Review [Services Comparison Cheat Sheet](cheat-sheets/02-services-comparison.md)
- [ ] Complete Domain 3 practice questions (Part 1)
- [ ] Hands-on: Create free tier account and explore services

#### Week 3: Advanced Services & Operations
- [ ] Read [AWS Cloud Fundamentals](docs/AWS-Cloud-Fundamentals.md) - Sections 8-10
  - AI/ML and Analytics
  - Security Services
  - Monitoring and Governance
- [ ] Review [Security & Compliance Cheat Sheet](cheat-sheets/03-security-compliance.md)
- [ ] Complete Domain 2 practice questions
- [ ] Hands-on: Set up IAM users, CloudWatch, and billing alerts

#### Week 4: Pricing & Review
- [ ] Read [AWS Cloud Fundamentals](docs/AWS-Cloud-Fundamentals.md) - Sections 11-13
  - Pricing and Support
  - Migration
  - Well-Architected Framework
- [ ] Review [Pricing & Support Cheat Sheet](cheat-sheets/04-pricing-support.md)
- [ ] Complete Domain 4 practice questions
- [ ] Take full-length mock exam
- [ ] Review incorrect answers and weak areas
- [ ] Final review of all cheat sheets

---

## Study Resources

### Included in This Repository

1. **[AWS Cloud Fundamentals](docs/AWS-Cloud-Fundamentals.md)** - Complete study guide covering all exam topics
2. **Practice Questions** - Domain-specific question sets with explanations
3. **Cheat Sheets** - Quick reference guides for rapid review
4. **[Study Tracker](STUDY-TRACKER.md)** - Track your progress through the material

### External Resources (Free)

- [AWS Cloud Practitioner Essentials](https://aws.amazon.com/training/digital/aws-cloud-practitioner-essentials/) - Official AWS training
- [AWS Skill Builder](https://explore.skillbuilder.aws/) - Free AWS learning platform
- [AWS Whitepapers](https://aws.amazon.com/whitepapers/) - Official documentation
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS Free Tier](https://aws.amazon.com/free/) - Hands-on practice

### External Resources (Paid)

- [A Cloud Guru](https://acloudguru.com/) - Video courses
- [Udemy AWS Courses](https://www.udemy.com/) - Practice exams
- [Tutorials Dojo](https://tutorialsdojo.com/) - Practice tests

---

## Quick Start Guide

1. **Clone or download this repository**
   ```bash
   git clone https://github.com/alanmaizon/swm.git
   cd swm
   ```

2. **Start with the fundamentals**
   - Read the [AWS Cloud Fundamentals](docs/AWS-Cloud-Fundamentals.md) guide
   - Follow the 4-week study plan above

3. **Track your progress**
   - Use [STUDY-TRACKER.md](STUDY-TRACKER.md) to monitor completion
   - Update checkboxes as you complete each section

4. **Practice regularly**
   - Work through practice questions daily
   - Take mock exams in the final week
   - Review incorrect answers thoroughly

5. **Use cheat sheets for review**
   - Quick review before exam
   - Reference during practice questions

---

## Key Topics to Master

### Must-Know Services

**Compute:**
- EC2, Lambda, Elastic Beanstalk

**Storage:**
- S3 (all storage classes), EBS, EFS

**Database:**
- RDS, DynamoDB, Aurora

**Networking:**
- VPC, CloudFront, Route 53

**Security:**
- IAM, Security Groups, KMS

**Monitoring:**
- CloudWatch, CloudTrail

**Billing:**
- Cost Explorer, Budgets, Support Plans

### Critical Concepts

1. **Shared Responsibility Model** - Know what AWS manages vs. customer
2. **Well-Architected Framework** - 6 pillars
3. **Pricing Models** - On-Demand, Reserved, Spot, Savings Plans
4. **Global Infrastructure** - Regions, AZs, Edge Locations
5. **Security Best Practices** - IAM, MFA, least privilege
6. **Service Comparisons** - S3 vs EBS vs EFS, etc.

---

## Exam Tips

### Before the Exam

- [ ] Get 7-8 hours of sleep
- [ ] Review cheat sheets (not full notes)
- [ ] Arrive 15 minutes early (or set up quiet space for online exam)
- [ ] Have water and snacks ready
- [ ] Review exam format and question types

### During the Exam

1. **Time Management**: ~83 seconds per question (65 questions / 90 minutes)
2. **Flag and Move On**: Don't get stuck on difficult questions
3. **Eliminate Wrong Answers**: Usually can eliminate 2-3 options
4. **Watch for Keywords**: "most cost-effective", "lowest latency", "cannot be interrupted"
5. **No Penalty for Guessing**: Answer every question
6. **Trust First Instinct**: Don't overthink

### Common Traps

- Confusing similar services (CloudWatch vs CloudTrail)
- Not reading "EXCEPT" or "NOT" in questions
- Overlooking keywords like "most", "least", "best"
- Choosing complex solutions when simple ones work
- Ignoring time/cost constraints in scenarios

---

## Practice Question Domains

### Domain 1: Cloud Concepts (24%)
- Benefits of AWS Cloud
- Cloud architecture design principles
- Migration strategies
- Economics of the cloud

### Domain 2: Security and Compliance (30%)
- Shared Responsibility Model
- AWS security services
- IAM best practices
- Compliance and governance

### Domain 3: Cloud Technology and Services (34%)
- Compute, storage, database, networking
- Analytics, machine learning, deployment
- Management and governance tools
- AWS global infrastructure

### Domain 4: Billing, Pricing, and Support (12%)
- Pricing models
- Cost management tools
- Support plans and resources
- Billing and cost optimization

---

## Mock Exam Strategy

1. **Simulate Real Conditions**
   - Full 90 minutes
   - No notes or references
   - Quiet environment

2. **Score and Review**
   - Score your exam
   - Review ALL questions (correct and incorrect)
   - Understand why each answer is right/wrong

3. **Identify Weak Areas**
   - Track which domains/topics you struggle with
   - Focus additional study on weak areas
   - Retake practice questions for weak topics

4. **Timing Practice**
   - Track time per question
   - Practice flagging and returning to questions
   - Ensure you can complete 65 questions in 90 minutes

---

## Frequently Asked Questions

**Q: How long should I study?**
A: Most candidates study 2-4 weeks with 1-2 hours daily. Adjust based on your background.

**Q: Do I need hands-on AWS experience?**
A: Not required, but recommended. Use AWS Free Tier to explore services.

**Q: What's the passing score?**
A: 700 out of 1000 (approximately 70%)

**Q: Can I use a calculator?**
A: Yes, a basic calculator is provided in the exam interface.

**Q: Are there scenario-based questions?**
A: Yes, expect scenarios requiring you to choose the best service/solution.

**Q: How technical is the exam?**
A: Foundation level - no coding, but understanding of service purposes and use cases.

---

## Contributing

This is a personal study repository, but if you find errors or have suggestions:

1. Open an issue describing the problem
2. Suggest improvements via pull request
3. Share additional study resources

---

## Additional Resources

### Official AWS Links

- [AWS Certification Homepage](https://aws.amazon.com/certification/)
- [CLF-C02 Exam Guide](https://d1.awsstatic.com/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Exam-Guide.pdf)
- [AWS Documentation](https://docs.aws.amazon.com/)
- [AWS Blog](https://aws.amazon.com/blogs/)

### Community

- [AWS subreddit](https://www.reddit.com/r/aws/)
- [AWS re:Post](https://repost.aws/)
- [AWS Community Builders](https://aws.amazon.com/developer/community/community-builders/)

---

## Certification Path

After passing Cloud Practitioner, consider:

**Associate Level:**
- Solutions Architect Associate
- Developer Associate
- SysOps Administrator Associate

**Professional Level:**
- Solutions Architect Professional
- DevOps Engineer Professional

**Specialty:**
- Security, Networking, Data Analytics, Machine Learning, etc.

---

## License

This repository is for educational purposes. AWS and related trademarks are property of Amazon.com, Inc.

---

## Updates

- **2026-01-02**: Repository initialized with comprehensive study materials
- Check back for updates to practice questions and cheat sheets

---

**Good luck with your exam preparation!** 🚀

Remember: Consistent daily study is better than cramming. Take breaks, stay hydrated, and believe in your preparation.
