# subnets-tf

**Info**
------
This Terraform module creates a range of subnets and associates them with a given route table.

**_Note:_** This module was originally created as my project team effort and was extended by me to meet additional requirements.

**Usage**
------
```python
module "nat" {
  source = "github.com/sebolabs/subnets-tf"

  project     = "lab"
  environment = "test"
  component   = "mgmt"
  name        = "nat"

  vpc_id             = "vpc-XXXXXXX"
  availability_zones = ["${data.aws_availability_zones.available.names}"]
  cidrs              = [
    "10.1.0.48/28",
    "10.1.0.64/28",
  ]
  map_public_ip_on_launch = false
  route_tables            = ["rtb-XXXXXXX"]
}
```

**Terraform compatibility**
------
TF versions tested: 0.9.11
