# Controlling your AWS costs by deleting unused Amazon EBS volumes

Solution based on this blog https://aws.amazon.com/blogs/mt/controlling-your-aws-costs-by-deleting-unused-amazon-ebs-volumes/

This solution will automate the available EBS volumes discovery, and create OpsItems using AWS System Manager

# Upload Lambda zip file to S3 Bucket

Upload Lambda zip file to S3 Bucket (make notation of bucket name and folder/zip file name)

e.g. S3 Bucket Name s3-cia-my-tf-test-bucket-lambda-001

    S3 Key Name lambdas/opsCenterAgedEBSVolumeFinder.zip

# Deploy Solution CloudFormation Template

Go to CloudFormation and create new stack using template file opsCenterAgedEBSVolumeFinder.yaml

This template will create 1) SNS Topic 2) Lambda Function 3) IAM Role for Lambda 4) EventBridge Rule based on Schedule

# Check the Solution blog for next steps

Review the OpsItems and run an Automation task on a non-compliant EBS volume

You can create your own custom Automation document for snapshotting and deleting a volume or simply deleting a volume as needed, and associate it to the OpsItems that are published by the Lambda function.

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

