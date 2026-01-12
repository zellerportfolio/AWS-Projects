# Project 03 – Secure Notes

**Status:** Planned  

A login protected Notes API that supports per user CRUD operations with strict data isolation.

---

## Goal

Build a secure, multiple user backend where only authenticated users can access their own data.

---

## Architecture **[PLANNED, may have final modifications]**

**Client**
→ **Cognito User Pool**
→ **API Gateway (Cognito Authorizer)**
→ **Lambda**
→ **DynamoDB**

---

## AWS Services Used

- Amazon Cognito (User Pools)
- Amazon API Gateway
- AWS Lambda
- Amazon DynamoDB
- AWS IAM
- Amazon CloudWatch

---

## Security Design

- Cognito authorizer at API Gateway
- User identity derived from token (`sub`)
- No client-supplied user IDs
- Least-privilege IAM

---

## API Capabilities

- Create, read, update, delete notes
- Per user data isolation
- Clean error handling (401 / 403 / 404)

---

## What This Demonstrates

- Authentication vs authorization
- Secure API design patterns
- Multiple tenant data modeling
- Zero trust backend architecture

---

## Key Insight

> Built a secured serverless Notes API on AWS using Cognito, API Gateway authorizers, Lambda, and DynamoDB with strict per user data isolation.
