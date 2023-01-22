# aws-github-actions-prepare-template
This is a template for creating resources for deployment to AWS with GitHub Actions.  
(The contents of this repository assume manual deployment.)

The following three resources are to be created.

1. OIDC Provider: Define to Assume Role with OIDC
1. IAM Role: Define to Assume Role using OIDC.
1. S3 Bucket: Used to place artifacts such as Lambda deployment packages

## Rquirements
- awscli
- sam-cli

## How To
1. edit template.yml
   - Edit L20 to limit the repositories that can touch your AWS environment with GitHub Actions
1. edit Makefile
   - Specify the CloudFormation Stack name in L3
1. exec deploy
   - Execute `make deploy` to create a Stack
1. check resources
   - Execute `make describe` to get the ARN and other information about the resource to be used in GitHub Actions