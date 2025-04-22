# Object Transformation with Amazon S3 Object Lambda

## Overview

This project demonstrates how to use Amazon S3 Object Lambda to dynamically modify the content of objects stored in S3 when they are requested by an application. By associating an AWS Lambda function with an S3 Object Lambda access point, it is possible to intercept GET requests and apply custom transformations to objects before sending them to the client.

In this example, the Lambda function transforms the content of the objects by converting all text to uppercase, illustrating a simple yet effective transformation that can be applied without modifying the original data in S3.

## Purpose

The purpose of this project is to show how the read behavior of S3 objects can be customized using Amazon S3 Object Lambda. By implementing a Lambda function, you can modify the way data is presented to consumers without duplicating or altering the data stored in S3.

This pattern is useful in scenarios where:

- Data needs to be adapted into different formats depending on the consumer.
- Filters, conversions, or validations should be applied prior to object delivery.
- You want to simplify client-side processing by keeping the transformation logic in the backend.

## Workflow

1. The application makes a GET request to the S3 Object Lambda access point.
2. S3 intercepts this request and routes it through the configured access point.
3. The request is sent to a custom AWS Lambda function.
4. The Lambda function reads the original object from the associated S3 bucket.
5. The object content is processed (in this case, converted to uppercase).
6. The transformed object is returned as a response to the initial request.

## Components Used

- **Amazon S3:** Stores the original data objects.
- **S3 Object Lambda Access Point:** Access point configured to intercept and redirect requests.
- **AWS Lambda:** Function that applies the transformation to the object.
- **IAM:** Roles and policies required to allow Lambda to access S3 and respond to requests.

## Requirements

- AWS account with permissions to create buckets, Lambda functions, and access points.
- AWS CLI or Management Console to configure the services.
- Python.
