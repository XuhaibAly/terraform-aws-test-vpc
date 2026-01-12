This is complete config to work with this module.


USAGE
```
provider "aws" {
  region = "us-east-2"
}

module "vpc" {
  source = "./module/vpc"

  vpc_cofig = {
    cidr_block = "10.0.0.0/16"
    name       = "your-vpc-name"
  }
    subnet_config = {
        public_subnet = {
        cidr_block = "10.0.0.0/24"
        az         = "us-east-2a"
        public_subnet = true
        }

         public_subnet-2 = {
        cidr_block = "10.0.2.0/24"
        az         = "us-east-2a"
        public_subnet = true
        }

        private_subnet = {
        cidr_block = "10.0.1.0/24"
        az         = "us-east-2b"
}
}
}
```