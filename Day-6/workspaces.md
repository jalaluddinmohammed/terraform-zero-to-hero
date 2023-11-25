## Workspaces basically solves the problem of isolation of statefile.
- It creates a separate state file for each workspaces ( Dev, Pre-Prod, PRD) etc..-
- If there are no workspace concept then the same state file would be used and it will be keep changing or updating existing resources.
![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/bc1225ba-c1e0-47b9-8e65-e1b84317315e)

- If you create a different tfvars file also, there is no use as the state file is common for all.


![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/8042f426-ca59-4e6d-a671-a042eeab864f)

- Now you create workspaces which creates a new folder and keep your state files under that.

![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/1d00990d-36c5-463a-b3bf-9d5bc40a8721)

- Now when you execute workspace create command for stage and PRD the you can see a file for stage and PROD is created.

  ![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/8504c96a-be57-4867-9cc1-415d2e20d283)


 ![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/b21ab795-071d-4d4d-abaf-59e225006684)

- Now you can select and switch to respective environment and perform your terraform actions (init,apply or destroy). In this example,i am creating the t2.micro instance.

![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/b1655e6d-3d1f-4ad8-b1d8-f888a16db7f5)

- New State file is created inside the workspace and not on root folder, its isolated with stage and PRD,and there is no impact if you do changes on dev.
![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/4ae21a27-3c51-4f88-a644-199be558771d)

- Now, you want to create resources on stage so you switch to it and run terraform apply, in this example i am changing instance_type from t2.micro to t2.medium, this will not change resource, but it will add.

 ![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/c5ae2c1b-4784-493a-ad44-01ec7b7e6b8e)

 ![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/0a8a4cd7-65cd-4b01-a742-275258b07552)

- We can see t2.micro is for DEV and t2.medium is for Stage. Existing infra is not changed as state file for stage and dev is different.
![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/ab77285d-80a1-45a4-9a98-08bee68aa88a)

- You can create different tfvars file for each environment ( dev.tfvars, stage.tfvars, prod.tfvars ..etc) then specify using terraform apply -var-file=dev.tfvars
- Also you can use a map inside VAR and specify values and write lookup. ( instance type is selected based on terraform.workspace value (dev, stage & prd), next is default t2.micro)
![image](https://github.com/jalaluddinmohammed/terraform-zero-to-hero/assets/145260536/de3e7480-2f92-4f7c-8a41-55687e1fc5ea)




 




