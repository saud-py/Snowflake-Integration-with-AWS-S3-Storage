# Snowflake-Integration-with-AWS-S3-Storage


## Objective:
Why to integrate the Snowflake Cloud Data Warehouse with AWS Cloud S3 Buckets to Access the files
Integrating Snowflake with AWS S3 Storage allows for efficient and secure data storage and management, making it a valuable tool for businesses that need to store and analyze large volumes of data.


## Prequites:
1. File Formats
2. Understanding on Stages Concepts
3. COPY INTO command
4. AWS Account

##Configuration 
#To establish a connection between Snowflake and AWS S3 Storage, the following configuration settings are required:
Define External Stages: Create a Cloud Storage Integration: In Snowflake, create a cloud storage integration to store an IAM user for AWS along with other parameters

Create an External Stage: Use the CREATE STAGE command in Snowflake to define an external stage that references the storage integration created earlier

Grant IAM User Permissions: Configure IAM access permissions in your AWS Management Console to allow the IAM user created by Snowflake to access bucket objects
2
.
Set Up File Formats:
Specify File Formats: When creating stages or loading data, include parameters such as FILE_FORMAT based on project-specific requirements and file formats
1
.
Specify Access Controls:
Configure Access Permissions for S3 Bucket: Create an IAM role in AWS with the necessary policies and permissions to access your S3 bucket containing data files
2
.
Grant IAM User Permissions: Grant the IAM user permissions to access bucket objects by configuring IAM access permissions in your AWS Management Console
2
.
Create Trust Relationship for Storage Integration: Execute queries in Snowflake to retrieve information about the storage integration, copy values of STORAGE_AWS_IAM_USER_ARN and STORAGE_AWS_EXTERNAL_ID, then grant access to the S3 storage integration by adjusting trust policy values in AWS
4
.

## Workflow
First there are files stored on the snowflake, we will transferring it to the AWS S3 with suitable integration will be transferred on the fly.
We will be creating necessary roles and policies and provide required authentication
We will also be creating objects in snowflake, such as Integration and External Stage Object.


![SF-S3 drawio](https://github.com/saud-py/Snowflake-Integration-with-AWS-S3-Storage/assets/57790931/1cb6c660-d854-4b6d-981a-817bf5bfda10)
