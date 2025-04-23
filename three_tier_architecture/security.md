# Security

## Access Control

- Access to EC2 instances is restricted by Security Group rules.
- Only the Load Balancer can route traffic to the instances.

## IP Restriction

- Direct access via the public IP of the EC2 instances is blocked.
- Access is only allowed through the Load Balancer DNS.

## IAM

### 🔧 Role for EC2 (`EC2MonitoringRole`)

**Attached Policy: `EC2MonitoringPolicy`**

Permissions:

- `logs:CreateLogStream`
- `logs:PutLogEvents`
- `logs:DescribeLogStreams`
- `cloudwatch:PutMetricData`
- `cloudwatch:GetMetricData`
- `cloudwatch:ListMetrics`

---

### 📈 Role for Auto Scaling (`AutoScalingExecutionRole`)

**Attached Policy: `AutoScalingPolicy`**

Permissions:

- `ec2:DescribeInstances`
- `ec2:TerminateInstances`
- `ec2:RunInstances`
- `autoscaling:UpdateAutoScalingGroup`
- `autoscaling:SetDesiredCapacity`
- `autoscaling:CreateAutoScalingGroup`
- `iam:PassRole`
