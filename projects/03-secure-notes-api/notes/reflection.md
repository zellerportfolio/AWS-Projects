# Project Reflection – Secure Notes API

## What problem does this solve in the real world?

This project solves the problem of securely storing and managing user-specific data in a multi-user backend system.

In real world applications, users expect that:
- Their data is private
- They cannot access other users’ data
- Authentication and authorization are handled consistently and securely

This Secure Notes API models a common backend pattern used by note taking apps, task managers, and personal data services, where each authenticated user can perform CRUD (Create, Read, Update, Delete) operations on their own data with strict isolation enforced by the backend.

---

## Why serverless instead of EC2?

Serverless services were a natural fit for this project because the workload is request-driven and stateless.

Using **API Gateway + Lambda + DynamoDB** provides:
- Automatic scaling with no infrastructure management
- Built-in integration with Amazon Cognito for authentication
- Pay-per-use pricing aligned with low, sporadic traffic
- Simple deployment and iteration without server maintenance

Using EC2 would have required managing instances, scaling policies, patching, and authentication logic manually, which would add unnecessary operational complexity for a small, secure API.

---

## What broke and how did I debug it?

The most challenging issues were related to **authentication, authorization, and request flow visibility**, rather than business logic.

Key problems encountered included:
- Receiving `401 Unauthorized` responses despite valid tokens
- Confusion around which Cognito token type (ID vs access token) was required
- API Gateway behavior differing between console tests and deployed stages
- Difficulty confirming whether requests were reaching Lambda

Debugging steps included:
- Verifying Cognito User Pool authorizer configuration in API Gateway
- Inspecting Lambda event payloads to confirm JWT (JSON Web Token) claims were injected correctly
- Printing and validating the `sub` claim used for per-user isolation
- Verifying deployed API Gateway stages and redeploying when necessary
- Using controlled `curl` requests to confirm authorization behavior

The root causes were primarily configuration related rather than code related, reinforcing how important it is to understand how AWS managed services interact at boundaries.

---

## What tradeoffs did I consciously make?

Several intentional tradeoffs were made to keep the project focused and aligned with its learning goals:

- Implemented a single Lambda handler instead of multiple micro-functions to reduce complexity
- Used API Gateway’s default domain instead of configuring a custom domain
- Deferred advanced monitoring, alarms, and dashboards to a future enhancement
- Avoided frontend UI to keep the scope backend focused
- Chose clarity and correctness over additional features like attachments or search

These decisions kept the project manageable and cost-aware.

---

## Key Takeaway

This project reinforced the importance of **clear security boundaries** in serverless architectures.

The most valuable lesson was that security in AWS is largely about **correct service integration and configuration**, not just code. By deriving user identity exclusively from JWT claims and enforcing isolation at both the API and data layers, the system maintains strong guarantees without unnecessary complexity.

This project strengthened my understanding of authentication vs authorization, multi-tenant data modeling, and practical serverless API design on AWS.
