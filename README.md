## Description
Deploys Udacity Instagram clone called Udagram.

## Setup

Step 1 - Network setup:
Creates network infrastructure in region us-west-2 (Oregon).

aws cloudformation create-stack --stack-name udagram-infra --template-body file://infra.yml --parameters file://infra-params.json --capabilities CAPABILITY_IAM --region us-west-2


Step 2 - Deploy Application Servers:
Deploys on AWS cloud web servers (t3.medium), picks up code (JavaScript and HTML) from S3 Storage and deploys it on the web server.

aws cloudformation create-stack --stack-name udagram-servers --template-body file://appservers.yml --parameters file://appservers-params.json --capabilities CAPABILITY_IAM --region us-west-2
