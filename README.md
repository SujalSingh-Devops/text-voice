🎙️ Serverless Text-to-Speech Pipeline
An automated, event-driven cloud pipeline that transforms text files into high-quality MP3 audio using AI-powered speech synthesis. This project demonstrates a production-ready serverless architecture on AWS.

🚀 Overview
This project automates the conversion of text to audio. When a .txt file is uploaded to a specific S3 bucket, it triggers a Lambda function that processes the text through Amazon Polly and stores the resulting audio file in a destination bucket.

Key Features
Event-Driven: Uses S3 Triggers to initiate processing instantly upon file upload.

AI Integration: Leverages Amazon Polly for natural-sounding neural text-to-speech.

Cost-Efficient: Built entirely on Serverless architecture (pay-only-for-what-you-use).

Automated Cleanup: Includes S3 Lifecycle Policies to manage storage and reduce costs.

🏗️ Architecture
S3 (Source Bucket): User uploads a .txt file.

Lambda: Triggered by the S3 "ObjectCreated" event.

Amazon Polly: Lambda sends text to Polly for synthesis.

S3 (Destination Bucket): Lambda saves the resulting .mp3 file.

CloudWatch: Logs all activity for monitoring and debugging.

🛠️ Tech Stack
Cloud Provider: AWS (S3, Lambda, Polly, IAM)

Language: Python 3.12

SDK: Boto3 (AWS SDK for Python)

🔧 Setup & Configuration
1. IAM Permissions
The Lambda function requires an IAM Role with the following managed policies:

AmazonS3FullAccess

AmazonPollyFullAccess

AWSLambdaBasicExecutionRole

2. Environment Variables
To keep the code modular, the following environment variables must be set in the Lambda configuration:

SOURCE_BUCKET: The name of your input bucket.

DESTINATION_BUCKET: The name of your output bucket.

📝 Usage
Upload a file named sample.txt to your Source S3 bucket.

The Lambda function will trigger automatically.

Retrieve your sample.mp3 from the Destination S3 bucket.
