# Project: Load Balancer with Auto Scaling

## Overview

This project implements an AWS architecture to balance traffic among multiple EC2 instances, redirecting requests to the instance with the lowest concurrency. The system also includes auto scaling policies (manual, scheduled, and dynamic), access restrictions by instance IP, and a single access path through the load balancer DNS.

## Objective

Ensure availability, scalability, and security of a group of EC2 instances through automated scaling and efficient traffic distribution.

## Workflow

1. An EC2 instance is launched from a Launch Template with Amazon Linux.
2. Upon startup, `stress`, a web server is automatically installed, and EFS is mounted to share content.
3. Instances are grouped in an Auto Scaling Group behind a Load Balancer.
4. Direct IP access is blocked, allowing only access through the Load Balancer DNS.
5. Three types of scaling are applied:
   - Manual (adjustment from the console).
   - Scheduled (by time).
   - Dynamic (based on CPU usage).
6. Load is simulated with `stress` to test the scaling behavior.
7. All instances access the same content via EFS.
8. The system is monitored with CloudWatch to maintain high availability.

## Components

- **Elastic Load Balancer (ELB):** Distributes incoming traffic.
- **EC2 Instances:** Host the application and report load/concurrency.
- **Auto Scaling Group (ASG):** Manages the instance lifecycle.
- **Launch Template:** Configures new instances.

## Requirements

- An active AWS account with permissions to create and manage resources such as:
  - EC2
  - ELB (Elastic Load Balancer)
  - Auto Scaling
  - IAM
  - CloudWatch
