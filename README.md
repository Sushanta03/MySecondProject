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
