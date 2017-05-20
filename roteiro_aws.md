# Initial

Documentation related about to Initial environment aws

(VPC)[http://docs.aws.amazon.com/cli/latest/reference/ec2/create-vpc.html]

## Network

VPC

```sh
aws ec2 create-vpc --cidr-block 10.0.0.0/16
```

Output

```sh
{
    "Vpc": {
        "VpcId": "vpc-286b9151",
        "InstanceTenancy": "default",
        "Tags": [],
        "Ipv6CidrBlockAssociationSet": [],
        "State": "pending",
        "DhcpOptionsId": "dopt-646cb802",
        "CidrBlock": "10.0.0.0/16",
        "IsDefault": false
    }
}
```

## Subnets

```sh
aws ec2 create-subnet --vpc-id vpc-a01106c2 --cidr-block 10.0.1.0/24
```