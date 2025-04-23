# Scheduled Deployment

Scheduled scaling was implemented to automatically adjust the number of instances based on predefined schedules, optimizing resources during traffic peaks.

## Implementation

1. **Launch Template with EFS:**

   - A Launch Template similar to the manual deployment was used, but with the difference that scaling is triggered automatically based on specifications.

![EFS Configuration](../images/EFS.jpg)

2. **Installing `stress`:**

   - To simulate load on the instances and test scaling behavior, `stress` was installed on the instances:
     ```bash
     sudo apt install -y stress
     ```

![Stress Instane](../images/stress_instance.jpg)

3. **Configuring the Auto Scaling Group (ASG):**

   - Scheduled scaling policies were configured using the AWS console

![Target group Programming](../images/target_group_programming.jpg)

4. **Testing with `stress`:**

   - During the project hours, `stress` was run on the instances to check how they responded to scaling.

5. **Access via Load Balancer:**
   - A Load Balancer was configured to handle incoming traffic, ensuring access is only made through its DNS, and direct IP access was blocked.

Load Balancer
![Load Balancer](../images/load_balancer.jpg)

Original
![Instance 1](../images/instance_1.jpg)

Replica 2
![Instance replica 2](../images/instance_replica_2.jpg)
![Instance 2](../images/instance_2.jpg)

Replica 3
![Instance replica 3](../images/instance_replica_3.jpg)
![Instance 3](../images/instance_3.jpg)

Replica 4
![Instance replica 4](../images/instance_replica_4.jpg)
![Instance 4](../images/instance_4.jpg)

Just using the navigator.
![Via Navigator](../images/navegator.jpg)

Register
![Registered targets](../images/registered_targets.jpg)

History
![Historial](../images/historial_prgm.jpg)

## Validation

- Verified that instances scaled correctly according to the scheduled time.
- Validated that new instances could access the shared content from EFS.
- Monitored the load on the instances using `stress` and verified the system's response.
