# Web Server with EC2 and Persistent Storage using EBS Snapshots

## Overview

This project uses Amazon EC2 and Amazon EBS to create a web server instance and generate snapshots of its volumes. The goal is to allow the instance to be safely terminated when not in use, reducing costs without losing stored data.

## Objective

Allow an EC2 instance to be safely terminated in order to save costs, while preserving the data in EBS volume snapshots and being able to restore it at any time.

## Workflow

1. An EC2 instance is launched with Amazon Linux.
2. Apache HTTP Server is automatically installed and configured at startup.
3. Additional EBS volumes are attached to the instance.
4. Snapshots of the volumes are created using the AWS Console.
5. The instance can be terminated without losing persistent data.

## Components Used

- **Amazon EC2**: For deploying and running the web server.
- **Amazon EBS**: For persistent data storage.
- **Amazon Machine Image (AMI)**: Based on Amazon Linux, with Apache HTTP Server configured.
- **EBS Snapshots**: For backing up the attached volumes.

## Requirements

- An active **AWS** account with permissions to manage EC2, EBS, and snapshots.
