# Project Reflection – Serverless URL Shortener

## What problem does this solve in the real world?

This project solves the problem of mapping long URLs to short, user friendly links while handling redirects efficiently.  
It mirrors real world use cases such as link sharing, campaign tracking, and API driven redirection services without requiring server management.

---

## Why serverless instead of EC2?

Serverless services remove the need to manage infrastructure, scaling, and patching.  
Lambda and API Gateway scale automatically with traffic, incur cost only when used, and are well suited for bursty, request driven workloads like URL shortening.

Using EC2 would introduce unnecessary operational overhead for a simple request/response API.

---

## What broke, and how did you debug it?

The primary issue was repeated `403 MissingAuthenticationTokenException` errors on the GET redirect endpoint.

Debugging steps included:
- Verifying API Gateway resource paths and methods
- Testing Lambda functions directly from the console
- Comparing console test behavior versus deployed stage behavior
- Recreating the GET method and redeploying the API
- Enabling CloudWatch logs for API Gateway

The root cause was a stale API Gateway deployment where configuration changes were not reflected in the active stage. Redeploying from the API root resolved the issue.

Additionally, using `curl -i` (GET with headers) instead of `curl -I` (HEAD request) helped confirm that the redirect behavior was functioning correctly at the HTTP layer.

---

## What tradeoffs did you consciously make?

- Used API Gateway default domain instead of a custom domain to avoid extra cost and complexity
- Chose API keys over Cognito for simplicity and scope control
- Implemented basic monitoring instead of full dashboards
- Deferred frontend UI in favor of API-first design

These tradeoffs kept the project focused, cost-aware, and aligned with its learning objectives.
