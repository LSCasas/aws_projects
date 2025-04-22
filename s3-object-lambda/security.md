## Security

To ensure the protection of data and proper access to resources in this project, several security measures were implemented following AWS best practices:

1. **IAM Policies for Lambda Function**
   IAM policies were configured specifically for the Lambda function, ensuring it only has **read** (`s3:GetObject`) permissions for objects in the S3 bucket. Additionally, permissions for **logging** in CloudWatch were enabled, allowing monitoring of the Lambda function.

2. **Access Control to Objects in S3**
   **Bucket policies** were established to restrict access to objects only to the Lambda function associated with the S3 Object Lambda access point. This ensures that only requests processed by the Lambda can access the stored data.

3. **Authorization of Access via S3 Object Lambda**
   The S3 Object Lambda access point was configured to ensure that only **GET requests**, managed by the Lambda function, can access the objects. This reinforces control over who can perform transformations and access the data.
