## Workspaces basically solves the problem of isolation.
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

