# Terraform Course

This repository contains hands-on examples for learning Terraform with AWS.

## Prerequisites

- [Terraform CLI](https://developer.hashicorp.com/terraform/install)
- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- An AWS account with permission to create the resources in the examples
- [Python](https://www.python.org/) 3.10 or later and [uv](https://docs.astral.sh/uv/) if you want to work with the Python project

## Set up the project

To create a new Python project, run `uv init` with the project name:

```bash
uv init 

```

This repository has already been initialized with uv, so you do not need to run `uv init` here. From the repository root, synchronize the Python environment:

```bash
uv sync
```

Configure AWS credentials using a secure method. For local development, AWS IAM Identity Center or another temporary-credential workflow is preferred. If you use access keys with `aws configure`, do not commit them to this repository. You can verify which AWS identity is active with:
Create a user group and user to set up aws configuration
```bash
aws configure
```

## Run the overview example

The example Terraform configuration is in `src/terraform_course/overview`. Run these commands from that directory:

```bash
cd src/terraform_course/overview
terraform init
terraform plan
terraform apply
```

Review the plan before applying it. Terraform will ask you to confirm before creating resources.

## Clean up

When you no longer need the resources, run this from the same directory:

```bash
terraform destroy
```

AWS charges may apply. Free Tier eligibility depends on your account and the resources you use, so check the AWS Billing console before applying changes.
