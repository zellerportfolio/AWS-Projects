# AWS Projects Portfolio

Welcome to my AWS Project Portfolio! This repository showcases hands-on AWS projects demonstrating my understanding of cloud infrastructure, security boundaries, and operational best practices.

These projects were built to reflect associate cloud engineering constraints, including least privilege access, cost awareness, and safe production design thinking.

## Certifications
- AWS Certified Solutions Architect Associate
- AWS Certified Cloud Practitioner

## 📂 Projects Overview

### 1️⃣ Resume Website on AWS (CloudFront + S3)
**Folder:** `01-resume-website-cloudfront`

A globally distributed, HTTPS secured static resume website using AWS native services.

**Key skills demonstrated**
- CDN architecture with CloudFront
- Private S3 origins (OAC)
- TLS certificates with ACM
- DNS with Route 53
- Security headers and HTTPS enforcement

### 2️⃣ Serverless URL Shortener
**Folder:** `02-serverless-url-shortener`

A Bitly style URL shortener built using a fully serverless backend.

**Key skills demonstrated**
- API Gateway (REST, Lambda proxy)
- AWS Lambda (Python)
- DynamoDB single-table design
- Least privilege IAM
- Structured logging & error handling

### 3️⃣ Secure Notes API (Authentication & Authorization)
**Folder:** `03-secure-notes-api`

A multi user, login protected Notes API with per user data isolation.

**Key skills demonstrated**
- Amazon Cognito (User Pools, JWT)
- API Gateway authorizers
- Secure Lambda backend design
- DynamoDB partitioning by user identity
- Zero-trust API design (no client-supplied user IDs)

## Design Philosophy

- **Serverless first** where appropriate
- **Least privilege IAM** everywhere
- **Security by default**, not as an afterthought
- **Clear separation of concerns**
- **Production style patterns**, even in small projects

## Notes

- Screenshots and reflections are included inside each project folder.

## Contact
LinkedIn: <https://www.linkedin.com/in/austinzeller/>

