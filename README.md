# 🚀 AWS CLI Portfolio – Secure Static Website 
This project demonstrates how to deploy a secure, static website on AWS using only the AWS CLI, following least-privilege security principles and Free Tier–safe architecture.

## Architecture
User --> HTTPS --> CloudFront (CDN + HTTPS) --> OAC  --> Private S3 Bucket (No public access)

## Key Features
- AWS CLI–only deployment (no console clicks)
- Private S3 bucket (public access fully blocked)
- CloudFront Origin Access Control (OAC) using SigV4
- HTTPS enabled via CloudFront default certificate
- Least-privilege IAM & bucket policy
- Free Tier–friendly (no EC2, no load balancers)

## Repository Structure

```
aws-cli-portfolio/
├── site/
│   ├── index.html
│   └── error.html
├── dist-config.json
└── README.md
```

# File Explanations
## 📁 site/
Contains the static website files deployed to S3.
### index.html
   - Main landing page of the website
   - Served as the default root object in CloudFront
   - Simple by design to focus on infrastructure and security

### error.html
   - Custom error page
   - Used for error handling in S3 / CloudFront configurations
   
## dist-config.json

- CloudFront distribution configuration file used with AWS CLI

This file defines:
- S3 origin configuration
- Origin Access Control (OAC)
- Cache behavior and policies
- HTTPS enforcement
- Viewer certificate settings
- Price class and performance settings


### README.md

Documentation explaining:
- Project purpose
- Architecture
- Security decisions
- File structure


## Validation
 - S3 objects verified via AWS CLI
 - CloudFront distribution status verified as Deployed
 - HTTPS endpoint tested successfully
 - Bucket access confirmed only via CloudFront

## Cleanup (Optional)
 - All resources can be safely deleted via AWS CLI to avoid charges:
 - S3 bucket
 - CloudFront distribution
 - Origin Access Control


## Next Enhancements (Optional)
 - Custom domain using Route 53
 - ACM certificate (CLI-managed)
 - CI/CD deployment via GitHub Actions
 - CloudFront logging and monitoring
