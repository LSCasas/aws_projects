# Security

## Access Control

- Access to EC2 instances is restricted by Security Group rules.
- Only the Load Balancer can route traffic to the instances.

## IP Restriction

- Direct access via the public IP of the EC2 instances is blocked.
- Access is only allowed through the Load Balancer DNS.

## IAM

- Specific roles and policies for:
  - EC2 (access to metrics, logs, monitoring)
  - Auto Scaling (instance creation and termination)
  - CloudWatch (metric reading)
