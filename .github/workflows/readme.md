## Overview

This directory includes the 3 Github actions jobs that can be used to deploy the required infrastructure to host the React SPA application in AWS. The jobs must be run in order for they will require resource Ids to be updated before running them.

### [deploy-certificate.yml](deploy-certificate.yml)

The Github Action job allows you to either Validate, Deploy or Destroy the cloudformation template. You must also select a region where you want it to be deployed. In this case, because we want to use the Certificate with a Cloudfront distribution, `the certificate MUST be deployed to us-east-1` (global). 

This Github Action is designed to create a new SSL certificate in AWS Certificate Manager, which will enable SSL connectivity for our website. Remember --> `us-east-1` 

Before running the Job (manual trigger), you must first have the following Github Repo Secrets setup:

1. `DEPLOYMENT_ROLE_ARN`
   - This must be an existing Role in your AWS account that will allow the job to run the `aws cloudformation deploy` command.
      - Typically, this role is granted Admin permissions in AWS. However, be aware that this could pose a security risk. AWS recommends using the least privileged permissions for enhanced security.
2. `HostedZoneId` and `HostedZoneName`
   - This is a pre-requisite before running the deployment. You must have a Route53 hosted zone (public) that will be used to create a CNAME with a friendly name for your website.
   -  

`Before deploying this to your AWS account, you must have a pre-existing Route53 public hosted zone in place, which is required for validating the certificate.`

### [spa.yml](/spa.yml)

This template is designed to create the following resources in your AWS account:

1. Private S3 bucket
2. Cloudfront distibution pointing to your S3 bucket from above.
3. Origin access point to allow S3 bucket access to the CDN.
4. Route53 dns friendly name for CDN.

`Before deploying this to your AWS account, you must have a pre-existing Route53 public hosted zone in place, which is required for creating the Route53 dns CNAME.`
   
