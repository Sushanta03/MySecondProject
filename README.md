# MySecondProject in AWS
My second project in AWS using services- Cloudformation,and SNS
Project : Publishing Amazon SNS Messages Privately
Objective

Build a secure healthcare notification system where:
Architecture:
Patient reports are stored securely
Messages are published privately using Amazon SNS
SNS is accessed from inside a VPC
EC2 instance sends notifications securely
Architecture:
EC2 Instance (Private/Public Subnet)
        │
        ▼
Amazon SNS Topic
        │
        ▼
Email / SMS / Mobile Push Notifications

Created a cloud formation stack for creation of ec2 with publishing SNS topic privately.
Connect to ec2 and install AWSCLI if Ubuntu system is being used(AWS CLI has been installed prebuilt in Amazon Linux)
sudo apt update -y
sudo apt install unzip curl -y
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws --version
SNS topic created using the command -> aws sns create-topic --name PatientReports
Subscribed email and published message-
aws sns subscribe \
--topic-arn arn:aws:sns:ap-south-1:123456789012:PatientReports \
--protocol email \
--notification-endpoint yourmail@gmail.com
aws sns publish \
--topic-arn arn:aws:sns:ap-south-1:123456789012:PatientReports \
--message "Patient report is ready securely."
aws sns list-topics
aws sns list-subscriptions
Verify email notification
