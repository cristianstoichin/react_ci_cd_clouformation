## Overview

This directory includes two AWS CloudFormation templates. These templates are executed by GitHub Actions to set up the necessary infrastructure for hosting the React SPA application.

### certificate.yml

This template is designed to create a new SSL certificate in AWS Certificate Manager, which will enable SSL connectivity for our website. 
`Before deploying this to your AWS account, you must have a pre-existing Route53 public hosted zone in place, which is required for validating the certificate.`

