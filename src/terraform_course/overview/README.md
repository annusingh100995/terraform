Initialize Terraform in the directory containing main.tf by running terraform init. This sets up the backend and state storage.
Run terraform plan to view the changes Terraform will make to your infrastructure.
Run terraform apply to create the specified resources. Confirm the action when prompted.
To clean up resources and avoid unnecessary costs, run terraform destroy and confirm the action when prompted.

# I have a free AWS account, so I can not provision all the instances.
# To check what instance are allowed, run the following command
#
# In us-east-1
'''
aws ec2 describe-instance-types \
  --filters "Name=free-tier-eligible,Values=true" \
  --region us-east-1 \
  --query "InstanceTypes[].InstanceType" \
  --output table

'''

'''

aws ec2 describe-instance-types \
  --filters "Name=free-tier-eligible,Values=true" \
  --region eu-north-1 \
  --query "InstanceTypes[].InstanceType" \
  --output table

  '''

 # I got the output, I'll use eu-north-1 and t3.micro 
 # I checked the ami that i can create for my account and i used that, the one given below.
 ami-083dedce92603a2ad
