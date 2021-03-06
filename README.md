# personal-blog
Personal blog development 

### Deploy status 
[![Actions Status](https://github.com/mtaracha/personal-blog/workflows/S3Deploy/badge.svg)](https://github.com/mtaracha/personal-blog/actions)

Repository aim is to be self contained, meaning it includes all needed code to build complete website. Main prerequisite is have Power User access to an AWS account. If you want to setup CI/CD then Github with Actions feature enabled is neccessary.

## Structure
- Terraform (v0.12.x) to build a S3 bucket to host static webpage (with CloudFront)
- Github Actions (Deployment pipeline to upload new s3 content on push to master)
- Blog website using HTML and JavaScript

## Development guidelines
- When working on infrastrcture development create `infra/*` branch which doesn't trigger app deployment

## Steps 

### S3 bucket for terraform state
Create using 
```
aws s3 mb s3://bucket-name
```

Terraform import bucket or Deploy User if you already have any of them created
```
terraform import aws_s3_bucket.bucket bucket-name
# or/and
terraform import aws_iam_user.deploy_user DeployUser
```

Blog code inspired by - https://github.com/learning-zone/website-templates/tree/master/startbootstrap-clean-blog-1.0.2

## To Do 
- See project [kanban board](https://github.com/mtaracha/personal-blog/projects/1)