## Security

The following security measures were implemented to protect the environment deployed in AWS:

- **Security Groups**

  - A security group was configured to allow HTTP access (port 80) from any IP address, ensuring public availability of the hosted website.

- **Key Pair**
  - An SSH key pair was used for authentication. The private key (`.pem`) was securely stored and used exclusively for administrative access to the EC2 instance.
