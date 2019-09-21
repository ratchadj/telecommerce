# Telecommerce

Telecommerce is a simple deployment Magento-CE-2.3.2 with sample data on the AWS Cloud. follow aws instructions.


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

## Magento Components

```
Operating system: Amazon Linux x86-64

Web server: NGINX

Database: Amazon RDS for MySQL 5.6

Programming language: PHP 7, including the required extensions
```

### Prerequisites

What things you need to install the software and how to install them

```
1. register aws consule account
2. install aws cli
3. run aws configure for storing access key and secret access key *** cat ~/.aws/credentials for checking your key
4. go to aws console and create secret key on AWS and put it on telecommerce/deployment/aws
```

### Deployment

A step by step series of examples that tell you how to get a development env running


```
cd telecommerce/deployment/aws
```

Then execute this file to create a project on AWS

```
aws cloudformation create-stack --stack-name telecommerce-stack --template-body file://$PWD/templates/magento-master.yaml --profile telecommerce --region ap-southeast-1 --capabilities CAPABILITY_NAMED_IAM
```

Then go to AWS consule and see progress in cloudformation menu and get URL after finish create stack in cloudformation.

for delete cloudformation stack able to excute this command.
```
aws cloudformation delete-stack --stack-name telecommerce-stack --profile telecommerce
```

## Running the tests

Go to AWS console then go to cloudformation and click your stack, you will see Outputs tab.
Access Magento Website by using URL.
Access Magento Admin Website by using AdminURL.
