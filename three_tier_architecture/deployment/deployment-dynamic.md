# Dynamic Deployment

Dynamic scaling was implemented to automatically adjust the number of instances based on actual resource usage, such as CPU and concurrency. This approach ensures the system can efficiently handle unexpected loads.

## Implementation

1. **Launch Template with EFS:**

   - The Launch Template includes the base configuration for the instances.

![EFS Configuration](../images/EFS.jpg)

2. **Installing `stress`:**

   - To test dynamic scaling, the `stress` tool was installed on the instances using the following command:
     ```bash
     sudo apt install -y stress
     ```

![Stress Instane](../images/stress_instance.jpg)

3. **Auto Scaling Group (ASG) Configuration:**

   - The ASG was configured with a minimum of 2 instances and a maximum of 4 instances.
   - Dynamic scaling policies were created based on the `CPUUtilization` metric:
     - **Scale up:** If CPU > 70% for 2 minutes, add one instance.
     - **Scale down:** If CPU < 30% for 5 minutes, remove one instance.

![Target group Dynamic](../images/target_group_dynamic.jpg)
![Dynamic scaling policies ](../images/dynamic_scaling.jpg)

4. **Load Generation with `stress`:**

   - During testing, artificial load was generated with `stress` to observe how the system responded:

5. **Access via Load Balancer:**
   - As with previous deployments, traffic can only access the instances through the Load Balancer's DNS, with direct IP access blocked.

Original
![Instance 1](../images/instance_1.jpg)

Replica 2
![Instance 2](../images/instance_2.jpg)

Replica 3
![Instance 3](../images/instance_3.jpg)

Just using the navigator.
![Via Navigator](../images/navegator.jpg)

History
![History](../images/historial_dymc.jpg)

## Validation

- Load was generated using `stress`, and it was observed how the ASG automatically scaled the number of instances.
- Verified that all instances accessed EFS content and responded correctly under load.
