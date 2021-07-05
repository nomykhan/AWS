# AWS
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 3.27"
    }
  }

  required_version = ">= 0.14.9"
}

provider "aws" {
  profile = "default"
  region  = "us-west-1"
  access_key = "XXXXXX"
  secret_key = "XXXXXX"
}

resource "aws_instance" "app_server" {
  ami           = "ami-01311df3780ebd33e"
  instance_type = "t2.micro"

  tags = {
    Name = var.instance_name
  }
}
