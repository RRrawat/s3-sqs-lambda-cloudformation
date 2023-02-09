# s3-sqs-lambda-cloudformation

Create a Lambda function that resizes images uploaded to S3 via SQS.

The SAM template deploys a Lambda function, an SQS queue, 2 S3 buckets and the IAM resources required to run the application.
An SQS queue consumes ObjectCreated events from an Amazon S3 bucket if the file has .jpg extension. The SQS triggers a Lambda function.
The Lambda code checks the uploaded file is an image and creates a thumbnail version of the image in another bucket.
