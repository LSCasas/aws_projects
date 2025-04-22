# Cost Report for Project Using AWS S3 Object Lambda (Single Day Usage)

The project utilizing **AWS S3 Object Lambda** to convert text to uppercase has been estimated for **one single day of usage**, with only **5 requests** made. Below are the calculated costs:

## 1. **GET Requests to S3**

- **Cost per 1,000,000 requests**: **$0.40 USD**
- **Cost per GET request**:  
  0.40 USD / 1,000,000 = 0.0000004 USD per request
- **Cost for 5 requests**:  
  5 \* 0.0000004 USD = 0.000002 USD

## 2. **Lambda Functions**

- **Cost per 1,000,000 Lambda executions**: **$0.20 USD**
- **Cost per Lambda execution**:  
  0.20 USD / 1,000,000 = 0.0000002 USD per execution
- **Cost for computation (1 second of execution and 512 MB)**:  
  8.35 USD / 1,000,000 = 0.00000835 USD per execution
- **Cost for 5 Lambda requests**:  
  5 \* (0.0000002 USD + 0.00000835 USD) = 0.00004175 USD

## 3. **Data Return**

- **Cost per 1,000,000 requests with 500 KB per object**: **$2.50 USD**
- **Cost per returned object (500 KB)**:  
  2.50 USD / 1,000,000 = 0.0000025 USD per object
- **Cost for 5 returned objects**:  
  5 \* 0.0000025 USD = 0.0000125 USD

## **Total Estimated Cost for 5 Requests in 1 Day**

- **GET Requests**: 0.000002 USD
- **Lambda Functions**: 0.00004175 USD
- **Data Return**: 0.0000125 USD

**Total cost for 5 requests**:  
0.000002 + 0.00004175 + 0.0000125 = 0.00005625 USD

## **Summary**

The total estimated cost for using the AWS S3 Object Lambda service during **one day with only 5 requests** is **approximately 0.00005625 USD**.

This cost is extremely low due to the limited number of requests and usage confined to a single day.
