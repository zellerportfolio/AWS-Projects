# Resume Website on AWS (CloudFront + S3)

A secure, globally cached resume website hosted entirely on AWS using native services.

---

## Goal

Host a fast, secure, custom domain resume site using AWS best practices for static content delivery.

---

## Architecture **[pending completion]**

**Browser**
→ **CloudFront (CDN + HTTPS)**
→ **Private S3 Bucket (Origin Access Control)**

**Route 53** handles DNS  
**ACM (us-east-1)** provides TLS certificates

---

## AWS Services Used

- Amazon S3 (private origin)
- Amazon CloudFront
- AWS Certificate Manager (ACM)
- Amazon Route 53

---

## Security Highlights

- S3 **Block Public Access enabled**
- CloudFront **Origin Access Control (OAC)**
- HTTPS enforced (HTTP → HTTPS redirect)
- Optional security headers (HSTS, CSP, X-Frame-Options)

---

## What This Demonstrates

- CDN-based web delivery
- Secure static hosting without public S3 access
- DNS + TLS integration
- Cost-efficient global architecture

---

## Validation

- Site loads over HTTPS
- Direct S3 access returns `AccessDenied`
- CloudFront invalidations propagate updates

---

## Key Insight

> Deployed a globally cached, HTTPS resume website on AWS using S3 (private origin), CloudFront, Route 53, and ACM with secure access controls and CDN best practices.
