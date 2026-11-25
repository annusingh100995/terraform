# Terraform Overview

Run the following commands from the directory containing `main.tf`.

## Initialize Terraform

Initialize Terraform and configure the backend:

```bash
terraform init
```

## Review and apply the changes

Run `terraform plan` to review the changes Terraform will make:

```bash
terraform plan
```

Run `terraform apply` to create the specified resources. Review the plan and confirm when prompted:

```bash
terraform apply
```

## Clean up resources

To clean up the resources and avoid unnecessary costs, run `terraform destroy` and confirm when prompted:

```bash
terraform destroy
```

## Check Free Tier-eligible instance types

I have an AWS Free Tier account, so I cannot provision every instance type. To check which instance types are marked as Free Tier-eligible, run the following command for the region you plan to use.

### `us-east-1`

```bash
aws ec2 describe-instance-types \
  --filters "Name=free-tier-eligible,Values=true" \
  --region us-east-1 \
  --query "InstanceTypes[].InstanceType" \
  --output table
```

### `eu-north-1`

```bash
aws ec2 describe-instance-types \
  --filters "Name=free-tier-eligible,Values=true" \
  --region eu-north-1 \
  --query "InstanceTypes[].InstanceType" \
  --output table
```

Based on the output, I will use the `eu-north-1` region and the `t3.micro` instance type. I checked which AMI I can use for my account and selected:

```text
ami-083dedce92603a2ad
```
