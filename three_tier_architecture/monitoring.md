# Monitoring

## Tools Used

To ensure optimal monitoring and performance tracking, the following tools were utilized:

- **Amazon CloudWatch:**  
  CloudWatch was used to monitor various system metrics such as concurrency, CPU usage, and network activity. These metrics provide detailed insights into the performance of the EC2 instances and overall infrastructure health, allowing for proactive resource management and issue detection.

- **Auto Scaling Metrics:**  
  The Auto Scaling Group (ASG) status and events were closely monitored to ensure that the application scales appropriately with demand. These metrics track the health and scaling actions of the ASG, providing real-time information about instance additions, terminations, and overall capacity management.

- **ELB Access Logs:**  
  Elastic Load Balancer (ELB) access logs were enabled to capture incoming traffic details and response times. These logs provide important data about the traffic distribution across the instances, helping in troubleshooting and performance analysis, particularly in identifying bottlenecks or unusual traffic patterns.
