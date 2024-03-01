# Snowflake-Integration-with-AWS-S3-Storage


## Objective:
Why to integrate the Snowflake Cloud Data Warehouse with AWS Cloud S3 Buckets to Access the files
Integrating Snowflake with AWS S3 Storage allows for efficient and secure data storage and management, making it a valuable tool for businesses that need to store and analyze large volumes of data.


## Prequites:
1. File Formats
2. Understanding on Stages Concepts
3. COPY INTO command
4. AWS Account

## Configuring Snowflake to Access AWS S3 Storage

## Step 1: Configure AWS IAM User and Role

1. Create an AWS IAM user for your Snowflake account.
2. Create an IAM role with the necessary permissions to access the S3 bucket.
3. Attach the IAM role to the IAM user created in step 1.

## Step 2: Create a Storage Integration in Snowflake

1. Create a storage integration in Snowflake with the following properties:
   - `storage_aws_role_arn`: The ARN of the IAM role created in step 1.
   - `storage_allowed_locations`: The location that the storage integration is allowed to access.
   - `enabled`: Set to true to enable the storage integration.

## Step 3: Create an External Stage

1. Create an external stage in Snowflake with the following properties:
   - `storage_integration`: The name of the storage integration created in step 2.
   - `url`: The URL of the S3 bucket (e.g., s3://<bucket_name>/).

## Step 4: Grant Access to the S3 Bucket

1. Configure the IAM policy to allow Snowflake to access the S3 bucket.
2. Attach the IAM policy to the IAM role created in step 1.

## Step 5: Test the Connection

1. Drop a file into the S3 bucket.
2. Run the following SQL statement in Snowflake to list the files in the S3 bucket:
   ```sql
   LIST @<stage_name>;

## Step 6: Use the External Stage
  - Use the external stage to load or unload data from the S3 bucket.

## Step 7: Manage File Formats
  - Create a file format in Snowflake to define the structure of the data files in the S3 bucket.
  - Use the file format when loading data from the S3 bucket.

## Step 8: Configure Access Controls
  - Use Snowflake's access controls to manage who can access the data in the S3 bucket.

##Step 9: Monitor and Manage the Integration
  - Monitor the integration for any issues or errors.
  - Manage the integration as needed, such as updating permissions or adding new stages.


## Workflow
First there are files stored on the snowflake, we will transferring it to the AWS S3 with suitable integration will be transferred on the fly.
We will be creating necessary roles and policies and provide required authentication
We will also be creating objects in snowflake, such as Integration and External Stage Object.

![SF-S3 drawio](https://github.com/saud-py/Snowflake-Integration-with-AWS-S3-Storage/assets/57790931/1cb6c660-d854-4b6d-981a-817bf5bfda10)
