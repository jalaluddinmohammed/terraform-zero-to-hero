# MIGRATION TO TERRAFORM & DRIFT DETECTION

https://youtu.be/-4IMy5ihiiU

# 1. Terraform migration ( using import and then running terraform import command which will create a state file).

- This will import the EC2 instance all details which was created manually.

  ![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/c5aa430b-7e1f-493d-988d-ed5c07358b71)


- Importing EC2 instance to create a state file.
![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/d02743d6-1ce4-462a-89f7-6cb7aef89e2c)


# 2. Terraform drift detection ( if some one manually changed any settings for any resource, then detecting that change is called drift detection).

# There are 2 ways to detect it.

Scenario 1: Use terraform refresh using a cron job. ( terraform refresh, refershes the recents changes which was done manually to the statefile and keeps it updated.

Scenario 2: 

- A) Use audit/activity logs to see who made changes, if its changed by user and resources is managed by TF, then send an alert using lambda/azure functions and notify.

- B) Apply strict IAM rules so that no one can login to console.
