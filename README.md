# Static Demo Site

Simple static website demonstrating automated deployment via GitHub Actions to AWS S3 and CloudFront.

**Live Site:** [https://d2jgqhup9totr6.cloudfront.net](https://d2jqghup9totr6.cloudfront.net)

---

## Overview

This is the frontend component of an automated infrastructure deployment pipeline. The site itself is minimal by design - the focus is on the infrastructure and deployment automation, not the web content.

**Infrastructure Repository:** [github.com/escanut/aws-terraform-s3-cloudfront-cicd](https://github.com/escanut/aws-terraform-s3-cloudfront-cicd)

---

## Tech Stack

- **HTML/CSS:** Vanilla (no frameworks)
- **Hosting:** AWS S3 static website
- **CDN:** CloudFront distribution
- **Deployment:** GitHub Actions with OIDC authentication
- **Infrastructure:** Terraform (see infrastructure repo)

---

## Project Structure

```
build/
├── index.html          # Main landing page
├── error.html          # 404 error page
└── style.css           # Styling
```

---

## Deployment

This site deploys automatically on push to the `main` branch via GitHub Actions:

1. Workflow triggers on commit
2. GitHub Actions assumes AWS IAM role via OIDC
3. Files sync to S3 bucket
4. CloudFront cache invalidated
5. Site live in ~30 seconds

No manual uploads. No AWS access keys stored.

---

## Local Development

```bash
# Serve locally (Python 3)
cd build
python3 -m http.server 8000

# Visit http://localhost:8000
```

---

## Key Features

- **Zero-downtime deployments** via CloudFront cache invalidation
- **HTTPS enabled** via CloudFront default certificate
- **Custom error handling** with styled 404 page
- **Mobile responsive** design
- **Automated timestamp** showing last deployment time

---

## Infrastructure Details

The site is hosted on infrastructure deployed via Terraform:

- S3 bucket with static website hosting enabled
- CloudFront distribution for global CDN
- IAM role with OIDC provider for GitHub Actions
- Least-privilege security policies

See the [infrastructure repository](https://github.com/escanut/aws-terraform-s3-cloudfront-cicd) for complete Terraform configuration and architecture documentation.

---

## Contact

**Victor Ojeje**  
GitHub: [github.com/escanut](https://github.com/escanut)  
Email: ojejevictor@gmail.com