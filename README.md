# ACIT4640-lab4

## Setup Instructions

Make sure terraform is installed locally

Ensure that you have an ssh key-pair, .pem locally and .pub as part of the terraform setup

### Update the starter code (main.tf) as follows:

tags need to be updated to include the project name

Availability zone needs to be configured to received public ip addresses

Gateway and route table need to be linked to the vpc and subnet, using the variable, like aws_vpc.web.id, which grabs the vpc_id based on earlier configurations

The aws_route block needs to reference the internet gateway correctly, using a cidr_block and route_table_id, referenced using the aws_route_table.web.id variable

Security group (aws_security_group) needs to reference the VPC ID, using aws_vpc.web.id to get the value

The EC2 settings need to be set, using the ami variable set earlier in the main code, as well as the instance type, subnet id, security group. We reference the public key in the .yaml file instead of declaring it directly in the ec2 block

### Terraform Commands

terraform init

terraform plan

terraform validate

terraform apply

### SSH generation command

ssh-keygen -t rsa -b 2048 -f ~/.ssh/my-aws-key