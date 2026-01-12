# Project 02 – URL Shortener

**Status:** Planned  

A Bitly-style URL shortener implemented using a fully serverless AWS architecture.

---

## Goal

Create a production style API that generates short URLs and redirects users efficiently.

---

## Architecture **[PLANNED, may have final modifications]**

**Client**
→ **API Gateway (REST, Lambda proxy)**
→ **Lambda (Python)**
→ **DynamoDB**

---

## AWS Services Used

- Amazon API Gateway
- AWS Lambda (Python 3.11)
- Amazon DynamoDB
- AWS IAM
- Amazon CloudWatch

---

## Security & Reliability

- Least-privilege IAM roles
- Conditional writes in DynamoDB to prevent collisions
- Input validation and error handling
- Structured logging for observability

---

## API Endpoints

- `POST /shorten` – Create short URL
- `GET /{code}` – 302 redirect to original URL

---

## What This Demonstrates

- Serverless backend design
- Stateless API patterns
- DynamoDB single-table access
- API Gateway Lambda proxy integration

---

## Key Insight

> Built a serverless URL shortener on AWS using API Gateway, Lambda, and DynamoDB with collision-safe writes, structured logging, and least-privilege IAM.
