## Overview

This directory includes the 3 Github actions jobs that can be used to deploy the required infrastructure to host the React SPA application in AWS. The jobs must be run in order for they will require resource Ids to be updated before running them.

### [deploy-certificate.yml](deploy-certificate.yml)

This template is designed to create a new SSL certificate in AWS Certificate Manager, which will enable SSL connectivity for our website. 

`Before deploying this to your AWS account, you must have a pre-existing Route53 public hosted zone in place, which is required for validating the certificate.`

### [spa.yml](/spa.yml)

This template is designed to create the following resources in your AWS account:

1. Private S3 bucket
2. Cloudfront distibution pointing to your S3 bucket from above.
3. Origin access point to allow S3 bucket access to the CDN.
4. Route53 dns friendly name for CDN.

`Before deploying this to your AWS account, you must have a pre-existing Route53 public hosted zone in place, which is required for creating the Route53 dns CNAME.`
   
