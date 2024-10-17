Install AWS CLI
```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```
Configure AWS CLI
```
AWS Access Key ID [None]: Access Key ID
AWS Secret Access Key [None]: Secret Access Key
Default region name [None]: region name
Default output format [None]: output format
```
Install Terraform
```
sudo yum install -y yum-utils shadow-utils
```
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
```
sudo yum -y install terraform
```

Set Up Terraform Project
```
mkdir first-project
cd first-project/
```
Create Terraform Configuration File
```
vi main.tf
```
Sample Terraform Configuration
```
provider "aws" {
    region = "us-east-1"
}

resource "aws_instance" "ec2" {
  ami = "ami-0a699202e5027c10d"
  instance_type = "t2.micro"
  tags = {
    Name= "terraform-instance-one"
  }
}
```
Terraform Commands
Initialize Terraform
```
terraform init
```
Validating Configuration
```
terraform validate
```
Executing the Plan
```
terraform plan
```
Applying the changes
```
terraform apply
```
Destroy the resources created by Terraform
```
terraform destroy
```
