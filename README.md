# AWS IoT Infrastructure CloudFormation Template

This repository contains a CloudFormation template designed to build an AWS infrastructure for an IoT data pipeline. The pipeline ingests IoT device data, processes it through Kinesis Data Streams and Firehose, applies Lambda functions for data transformation and storage, saves data in MariaDB and S3 buckets, and integrates with SageMaker for machine learning model training and inference. The processed data and model outputs are presented via a website hosted on S3.

This template provides the majority of services required for an end-to-end IoT data processing and analytics solution using AWS.

## Prerequisites

- An AWS account with appropriate permissions.  
- AWS CLI installed and configured.

## AWS CLI Installation

Please refer to the official AWS CLI installation guide:  
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html

## Deployment Instructions

1. **Clone this repository**

    Open a terminal and run:

    ```bash
    git clone https://github.com/nnhida/cf-iot-templates.git
    cd cf-iot-templates
    ```

2. **Prepare your parameters file**

    Create a parameters file (in JSON or YAML format) containing all the required parameter values needed by the CloudFormation template.

3. **Deploy the CloudFormation stack**

    Use the AWS CLI to deploy the stack by running:

    ```bash
    aws cloudformation deploy \
      --template-file template.yml \
      --stack-name stackname \
      --parameter-overrides file://parameters.yml
    ```

    - Replace `template.yml` with the path to your CloudFormation template file.  
    - Replace `parameters.yml` with the path to your parameters file.  
    - Replace `stackname` with your preferred stack name.

4. **Verify the stack deployment**

    Check the status of the deployment either via the AWS Management Console or by running:

    ```bash
    aws cloudformation describe-stacks --stack-name stackname
    ```

## Notes

- Ensure your parameters file includes all required parameters with valid values.  
- This template covers core AWS services for setting up an IoT data ingestion and analytics pipeline.  
- Feel free to modify the template and parameters to better suit your specific requirements.
