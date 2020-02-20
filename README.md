# ami

Amazon Machine Image is used to deevlop cusomised EC2 instances.
The project aims at developing an AMI template by installing all the necessary softwares needed for hosting the application on EC2 instance.

## Getting Started

1. add a space in README file
2. Create a Pull request with master branch of organization
3. The cricleci build will get triggered on merge which will use packer to create AMI on AWS
4. Use this AMI to create EC2 instance and configure the security group and open port 8080 for TCP and port 80 for HTTP


### Prerequisites

1. Have used hashicorp/packer:1.1.1 image for installing packer on circleci


End with an example of getting some data out of the system or using it for a little demo

## Running the tests

   packer validate \
              -var "aws_region=${AWS_REGION}" \
              -var "aws_access_key=${AWS_ACCESS_KEY_ID}" \
              -var "aws_secret_key=${AWS_SECRET_ACCESS_KEY}" \
              -var "source_ami=${source_ami}" \
              -var "ami_users=${ami_users}" \
              -var "ssh_username=${ssh_username}" \
              ubuntu-ami.json

    packer build \
              -var "aws_region=${AWS_REGION}" \
              -var "aws_access_key=${AWS_ACCESS_KEY_ID}" \
              -var "aws_secret_key=${AWS_SECRET_ACCESS_KEY}" \
              -var "source_ami=${source_ami}" \
              -var "ami_users=${ami_users}" \
              -var "ssh_username=${ssh_username}" \
              ubuntu-ami.json