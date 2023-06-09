# certified-terraform-associate
This repo is agregated guide for preparation to Hashicorp terraform associate exam

## How to book your exam

<details>
<summary>exam booking guide</summary><br><b>
  
* https://www.youtube.com/watch?v=NOXKviWY6oc
  
* https://www.hashicorp.com/certification/terraform-associate
</b></details>

<details>
<summary>Check list before exam</summary><br><b>
  
 * https://developer.hashicorp.com/terraform/tutorials/certification/associate-review
</b></details>

## Example questions


<b>How can you reference all of the subnets that are created by this resource block?</b>


```
#Deploy the private subnets
resource "aws_subnet" "private_subnets" {
  for_each          = var.private_subnets
  vpc_id            = aws_vpc.vpc.id
  cidr_block        = cidrsubnet(var.vpc_cidr, 8, each.value)
  availability_zone = tolist(data.aws_availability_zones.available.names)[each.value]
 
  tags = {
    Name      = each.key
    Terraform = "true"
  }
}
```
<details>
<summary>Answer</summary><br><b>

  ```aws_subnet.private_subnets[*]```

</b></details>

<b>What two options are available to delete all of your managed infrastructure?</b>

<details>
<summary>Answer</summary><br><b>

 * ```terraform destroy```
 * ```terraform apply -destroy```

</b></details>

<b>Which option will you use to run provisioners that are not associated with any resources?</b>

A. Local-exec
  
B. Null_resource
  
C. Salt-masterless
  
D. Remote-exec


<details>
<summary>Answer</summary><br><b>

Option B is correct
If you need to run provisioners that aren’t directly associated with a specific resource, you can associate them with a null_resource.

</b></details>




