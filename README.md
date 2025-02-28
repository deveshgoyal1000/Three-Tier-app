﻿# AWS Three Tier Web Architecture

## Description:
This project is a hands-on walk through of a three-tier web architecture in AWS. We will be manually creating the necessary network, security, app, and database components and configurations in order to run this architecture in an available and scalable manner.

## Audience:
It is intended for those who have a technical role. The assumption is that you have at least some foundational aws knowledge around VPC, EC2, RDS, S3, ELB and the AWS Console.

## Pre-requisites:
- An AWS account. If you don't have an AWS account, follow the instructions here and click on "Create an AWS Account" button in the top right corner to create one.
- IDE or text editor of your choice.

## Architecture Overview
![Architecture Diagram](demos/3TierArch.png)

In this architecture, a public-facing Application Load Balancer forwards client traffic to our web tier EC2 instances. The web tier is running Nginx webservers that are configured to serve a React.js website and redirects our API calls to the application tier's internal facing load balancer. The internal facing load balancer then forwards that traffic to the application tier, which is written in Node.js. The application tier manipulates data in an Aurora MySQL multi-AZ database and returns it to our web tier. Load balancing, health checks and autoscaling groups are created at each layer to maintain the availability of this architecture.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author
[Devesh Goyal](https://github.com/deveshgoyal1000)
