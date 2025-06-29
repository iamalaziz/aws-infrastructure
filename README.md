# AWS Infrastructure as Code — CloudFormation Stack

This repository contains an **AWS CloudFormation template** for deploying a complete cloud infrastructure to host applications in the AWS cloud. This template is primarily designed for test environments. The default parameters allocate smaller resources to help minimize costs during testing.

The template is validated using [cfn-lint](https://github.com/aws-cloudformation/cfn-lint) and formatted with [rain](https://github.com/aws-cloudformation/rain) for readability and best practices compliance.

&nbsp;

## 📑 Overview

This CloudFormation stack provisions:

✅ A Virtual Private Cloud (VPC) architecture with private subnets  
✅ Networking components (Internet Gateway, routing, security groups)  
✅ S3 buckets for uploads and caching  
✅ Secrets management with AWS Secrets Manager  
✅ IAM roles and policies for secure resource access  
✅ Elastic Beanstalk application environment for app deployment  
✅ Elastic Beanstalk configuration with:

- Auto-scaling
- HTTPS support via ACM
- CloudWatch log streaming
- Health checks
- Rolling updates and managed platform updates

✅ PostgreSQL RDS instance with enhanced monitoring  
✅ ACM certificate for HTTPS endpoints  

&nbsp;

## ⚙️ Parameters

The template accepts several parameters for customization:

| Parameter           | Description                                                       |
|----------------------|-------------------------------------------------------------------|
| **RootStackName**    | The root stack name used as a prefix for resources.               |
| **HostedZone**       | ID of the Route53 Hosted Zone for domain configuration.           |
| **PinpointApp**      | Amazon Pinpoint Project ID for analytics integrations.           |
| **EC2InstanceType**  | EC2 instance type for Elastic Beanstalk environment (e.g., t3.small). |
| **DBInstanceType**   | RDS instance type (e.g., db.t3.micro).                            |
