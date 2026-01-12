# Secure Static Website with Amazon S3 & CloudFront

## Goal
Deliver static content securely using AWS managed services with minimal operational overhead.

## Architecture
S3 private bucket → CloudFront distribution → HTTPS delivery

## Key Design Decisions
- Private S3 bucket (no public access).
- CloudFront as the only access path.
- Cost-aware caching behavior.
- Logging enabled for visibility.

## Acceptance Checklist
- [ ] Website accessible via CloudFront URL
- [ ] S3 bucket not publicly accessible
- [ ] Logs visible in CloudWatch/S3
- [ ] Resources cleaned up after testing

## Portfolio Evidence
- Architecture diagram [pending]
- CloudFront distribution screenshot [pending]
- Access control configuration [pending]

## Cleanup
All resources deleted after validation to avoid cost.
