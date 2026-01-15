# AWS Projects Portfolio

Welcome to my AWS Projects Portfolio. This repository contains hands-on, production style cloud projects built using AWS managed services, with a strong focus on security boundaries, serverless architecture, and operational correctness.

All projects are designed within **associate level cloud engineering constraints**, emphasizing:
- Least privilege access
- Cost awareness and Free Tier alignment
- Secure-by-default architecture
- Clear separation of responsibilities between services

---

## Certifications

- **AWS Certified Solutions Architect Associate**
- **AWS Certified Cloud Practitioner**

---

## 📂 Projects Overview

### 1️⃣ Resume Website on AWS (CloudFront + Private S3)
[View Project](projects/01-resume-website-cloudfront)

A globally distributed, HTTPS secured static resume website built using AWS native services and modern CDN best practices.

**Key skills demonstrated**
- Content delivery using Amazon CloudFront
- Private Amazon S3 origins secured with Origin Access Control (OAC)
- HTTPS enforcement via CloudFront managed certificates
- Cost-aware static site hosting
- Secure origin design preventing direct object access

---

### 2️⃣ Serverless URL Shortener API
[View Project](projects/02-serverless-url-shortener)

A Bitly style URL shortener implemented using a fully serverless backend on AWS.

**Key skills demonstrated**
- Amazon API Gateway (REST API, Lambda proxy integration)
- AWS Lambda (Python 3.11)
- DynamoDB single table access patterns
- Conditional writes for data integrity
- Least privilege IAM execution roles
- Input validation and defensive error handling
- Real world troubleshooting of API Gateway and Lambda behavior

---

### 3️⃣ Secure Notes API (Authentication & Authorization)
[View Project](projects/03-secure-notes-api)

A secure, multi-user Notes API where authenticated users can create, read, update, and delete their own data with strict per-user isolation.

**Key skills demonstrated**
- Amazon Cognito User Pools for authentication
- JWT (JSON Web Token) based authorization enforced at API Gateway
- Secure Lambda backend design with identity derived from token claims
- Multi-tenant data modeling in DynamoDB
- Zero trust API design (no client supplied user identifiers)
- Clean, explicit error handling for unauthorized and invalid access

---

## Design Philosophy

Across all projects, I prioritize:

- **Serverless-first architecture** where appropriate
- **Least privilege IAM** as a baseline requirement
- **Security by default**, not as an afterthought
- **Clear service boundaries and responsibility separation**
- **Production style patterns**, even in small scale systems
- **Operational clarity**, favoring correctness over unnecessary complexity

---

## Repository Notes

- Each project folder contains:
  - Architecture diagrams
  - Deployment screenshots
  - Source code (where applicable)
  - A detailed README explaining design decisions
  - A written reflection covering tradeoffs and debugging lessons

These projects are intended to reflect how real world AWS systems are designed, secured, and reasoned about, rather than optimized purely for feature count.

---

## Contact
LinkedIn: <https://www.linkedin.com/in/austinzeller/>

