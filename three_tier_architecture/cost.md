# Cost Report for Load Balancer with Auto Scaling (Single Day Usage)

This report estimates the cost of running a **load balancer with auto scaling** for **one single day**, with **2 EC2 instances active**, handling traffic through the **Elastic Load Balancer (ELB)** and being monitored using **CloudWatch**.

## 1. **EC2 Instances (t3.medium)**

- **Hourly rate per instance (on-demand)**: **$0.0416 USD**
- **2 instances for 24 hours**:  
  2 \* 24 \* 0.0416 = **$1.9968 USD**

## 2. **Elastic Load Balancer (Application Load Balancer)**

- **Hourly cost**: **$0.0225 USD**
- **Cost per GB processed**: **$0.008 USD** (assume 1 GB)
- **Total ELB cost for 24 hours and 1 GB traffic**:  
  (24 \* 0.0225) + 0.008 = **$0.548 USD**

## 3. **CloudWatch Metrics**

- **Custom metrics (3 metrics)**:  
  $0.30 USD per metric per month → ~$0.01/day/metric  
  3 \* 0.01 = **$0.03 USD**
- **CloudWatch Logs ingestion (1 MB)**:  
  $0.50 per GB → 0.0005 USD per MB  
  1 MB = **$0.0005 USD**

## 4. **Auto Scaling Group**

- **Auto Scaling itself has no cost**, only EC2 costs apply.
- Any instance launched by Auto Scaling counts as regular EC2 billing.

---

## **Total Estimated Cost for One Day**

- **EC2 Instances**: $1.9968 USD
- **Elastic Load Balancer**: $0.548 USD
- **CloudWatch Metrics**: $0.03 USD
- **CloudWatch Logs**: $0.0005 USD

**Total estimated cost for one day**:  
**$1.9968 + $0.548 + $0.03 + $0.0005 = $2.5753 USD**

---

## **Summary**

The total estimated cost for running the **Load Balancer with Auto Scaling and Monitoring** for a single day with basic traffic and monitoring is **approximately $2.58 USD**.
