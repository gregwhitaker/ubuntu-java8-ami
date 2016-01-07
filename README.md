ubuntu-java8-ami
===

Packer configuration that creates an Ubuntu 14.04 AMI with Java8 installed as the default Java Runtime Environment.

##Variables

###Required

* `aws_access_key` - Access key of the AWS where the AMI will be created.

* `aws_secret_key` - Secret key of the AWS where the AMI will be created.

* `aws_region` - Name of the AWS region where the AMI will be created.

###Optional

* `aws_vpc_id` - Id of the VPC where the AMI will be created.  If a value is not specified the AMI will be built in the default VPC.

* `aws_subnet_id` - Id of the Subnet where the AMI will be created.  If a value is not specified the AMI will be built in the default subnet.

##Usage

###Create AMI in the Default VPC

```
$ packer build -var 'aws_access_key={account access key} \
     -var 'aws_secret_key={account secret key} \
     -var 'aws_region={aws region}
     packer.json
``` 

###Create AMI in a Specific VPC

```
$ packer build -var 'aws_access_key={account access key} \
     -var 'aws_secret_key={account secret key} \
     -var 'aws_region={aws region} \
     -var 'aws_vpc_id={aws vpc id} \
     -var 'aws_subnet_id={aws subnet id} \
     packer.json
``` 