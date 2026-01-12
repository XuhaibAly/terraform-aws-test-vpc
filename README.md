# terraform-aws-vpc

### Overview

This Terraform module creates an AWS VPC with given CIDR block. It also creates multiple subnets (public and private), and for public subnets, it sets up Internet Gateway (IGW) and appropriate route tables.


## Features

-- Creates a VPC with a apecified CIDR block
-- Creates public and private subnets
-- Creates an Internet Gateway (IGW) for public subnets
-- Sets up route tables for public subnets


## Usage
```
module "vpc" {
  source = "./module/vpc"

  vpc_cofig = {
    cidr_block = "10.0.0.0/16"
    name       = "your_vpc_name"
  }
    subnet_config = {
        public_subnet = {
        cidr_block = "10.0.0.0/24"
        az         = "us-east-2a"
        # To set the subnet as public, default is private
        public_subnet = true
        }

        private_subnet = {
        cidr_block = "10.0.1.0/24"
        az         = "us-east-2b"
}
}
}
```