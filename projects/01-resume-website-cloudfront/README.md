# Resume Website on AWS (CloudFront + Private S3)

Deployed a globally cached, secure static resume website hosted on AWS using Amazon CloudFront with a private Amazon S3 origin.

---

## Project Goal

Deploy a production style static website using AWS native services that demonstrates:

- CDN based content delivery
- Secure private object storage
- HTTPS via managed CloudFront certificates
- Real world cloud architecture patterns for static sites

---

## Current Architecture (Deployed)

**User / Browser**  
→ **Amazon CloudFront Distribution (CDN + HTTPS)**  
→ **Private Amazon S3 Bucket (Origin Access Control)**  

- The site is accessed using the **CloudFront default domain**
- HTTPS is provided by **CloudFront’s managed certificate**
- The S3 bucket is **not publicly accessible**
- All content is served **only through CloudFront**

> Direct access to S3 object URLs returns `AccessDenied`, enforcing least privilege access.

---

## AWS Services Used

- **Amazon S3**
  - Hosts static HTML and CSS site files created locally via CloudShell
  - Block Public Access enabled
  - Default encryption enabled
- **Amazon CloudFront**
  - Global CDN
  - HTTPS termination
  - Caching and origin protection via Origin Access Control (OAC)

> No custom domain since this is a portfolio piece, Route 53 records, or ACM certificates were configured in the current build.

---

## Security Characteristics

- S3 **Block Public Access** enabled
- CloudFront **Origin Access Control (OAC)** restricts S3 access
- HTTPS enforced via CloudFront default domain
- Direct S3 access blocked (`AccessDenied`)

This mirrors real world patterns used to prevent direct object exposure.

---

## Validation & Testing

- Site successfully loads over HTTPS through CloudFront
- CloudFront serves cached or fresh content correctly
- Direct S3 URLs are inaccessible
- Content updates propagate after CloudFront invalidation using CloudShell

---

## What This Project Demonstrates

- Static website hosting on AWS without public S3 access
- CDN-based architecture using CloudFront
- Secure origin design using Origin Access Control
- Practical understanding of AWS content delivery fundamentals
- Cost-aware architecture suitable for Free Tier learning

---

## Future Enhancements (Not Implemented)

The following were intentionally scoped as future improvements:

- Custom domain using **Amazon Route 53**
- TLS certificate management using **AWS Certificate Manager (ACM)**
- HTTP security headers via **CloudFront Functions**
- CI/CD deployment using GitHub Actions or AWS CodePipeline
- Access logging and monitoring

These enhancements are reflected in the optional architecture diagram but were **not part of the deployed build**.

---

## Architecture

### Current Implementation

[Core architecture](diagrams/core-diagram-architecture.png)

### Optional Future Enhancement

[Optional architecture](diagrams/optional-diagram-architecture.png)

---

## Deployment Screenshots

### CloudFront Distribution

[CloudFront distribution](screenshots/CloudFront-Distribution-for-Resume-Site.png)

### Site Live via CloudFront

[Live site](screenshots/CloudFront-Distribution-Domain-Live-Resume-Site.png)

### Direct S3 Access Blocked

[S3 access denied](projects/01-resume-website-cloudfront/screenshots/S3-direct-access-denied-to-resume-site.png)

---

## Key Takeaway

> Built a secure, globally distributed static website on AWS using CloudFront with a private S3 origin, demonstrating CDN caching, origin protection, and HTTPS delivery without exposing public object storage.
