# terraform-
# Terraform Infrastructure Deployment #
This Terraform configuration automates the deployment of a basic AWS infrastructure in the us-east-1 region. It includes the creation of a VPC, subnets, security group, EC2 instance running Tomcat, SNS topic, SNS subscription, Application Load Balancer (ALB), Auto Scaling Group, Launch Configuration, CloudWatch alarm, and necessary routing configurations.

# Prerequisites #
Before applying this Terraform configuration, ensure you have:

AWS CLI configured with appropriate access credentials.
Terraform installed on your local machine.
# Configuration Overview #
# Files Included:
main.tf: Defines the AWS provider, variables, resources, and outputs.
variables.tf: Declares variables used in the configuration.
output.tf: Defines outputs for the deployed resources.
# Configuration Details:
AWS Provider Configuration:
Specifies the AWS region for deployment.
- `Variables`:
Defines variables for VPC CIDR block, subnet CIDR block, key pair name, private key path, and email address for SNS notifications.
- `VPC Setup`:
Creates a VPC with the specified CIDR block.
Attaches an Internet Gateway to enable internet access.
- `Subnets`:
Defines two subnets across different availability zones within the VPC.
- `Security Group`:
Configures a security group allowing inbound traffic on ports 22, 80, and 8080, and all outbound traffic.
- `EC2 Instance`:
Launches an EC2 instance with Ubuntu, associating it with a subnet and security group.
Installs Java and Tomcat using user data script.
Configures SSH connection and remote-exec provisioner.
- `AMI Creation`:
Creates a custom AMI from the EC2 instance for future use.
- `SNS Topic`:
Creates an SNS topic named "MyTopic".
- `SNS Subscription`:
Subscribes an email endpoint to the SNS topic for notifications.
- `Application Load Balancer (ALB)`:
Deploys an ALB to distribute incoming traffic across EC2 instances.
- `Auto Scaling Group (ASG)`:
Creates an ASG with a desired capacity of 0 instances initially.
- `Launch Configuration`:
Configures the launch configuration for instances in the ASG.
Installs Java and Tomcat using user data script.
- `CloudWatch Alarm`:
Sets up a CloudWatch alarm to monitor CPU utilization of the EC2 instance.
- `Routing Configuration`:
Updates the route table to route traffic through the Internet Gateway.
Associates a subnet with the route table.
- `Outputs`:
Outputs the DNS name of the ALB for accessing the deployed application.
# Usage #
Clone this repository to your local machine.
Navigate to the directory containing the Terraform files.
Initialize Terraform with terraform init.
Review and modify the variables in variables.tf if needed.
Apply the configuration with terraform apply.
Confirm the changes and type "yes" to proceed with the deployment.
Wait for Terraform to provision the infrastructure.
Once completed, Terraform will output the DNS name of the ALB for accessing the deployed application.
# Cleanup #
To tear down the deployed infrastructure, run terraform destroy and confirm the destruction of resources.


