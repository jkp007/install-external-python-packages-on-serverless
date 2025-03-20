# Steps - Create IAM User

Username - athena-report

Click next

Choose - Attach policies directly

1. AWSLambdaBasicExecutionRole
2. athena:ListQueryExecutions [athena-report > Permissions > Create Inline Policy > Services (Athena) > Allowed Object (ListQueryExecutions) > Resources (All) > Next provide a policy name and create]
3. s3:PutObject [athena-report > Permissions > Create Inline Policy > Services (s3) > Allowed Object (PutObject) > Resources (All) > Next provide a policy name and create]
4. athena:BatchGetQueryExecution [athena-report > Permissions > Create Inline Policy > Services (Athena) > Allowed Object (BatchGetQueryExecution) > Resources (All) > Next provide a policy name and create]

# Steps to configure AWS CLI

Go to AWS console > Go to IAM > Open athena-report > Security credentials > Create Access key > Select "Command Line Interface (CLI)" > Access Key created and store them in csv format

# Command to configure AWS CLI [ Installatin Guide - https://docs.aws.amazon.com/cli/v1/userguide/install-linux.html#install-linux-pip ]

```
aws configure
```

AWS Access Key ID [None]: ID
AWS Secret Access Key [None]: Key
Default region name [None]: us-east-1 [Choose Region]
Default output format [None]: json

# Create S3 bucket to store the Athena Report Data

Go to AWS console > Go to IAM > Create Bucket > General Purpose > Provide name - athena-report-data > athena_result/

Created 3 folders
sample_data/ -> Contains the data to query by athena
athena_result/ -> Store the athena query results
report_data/ -> To store the athena usage data using AWS lambda
