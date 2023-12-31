# Azure Terraform           
          
![image](https://github.com/Pavan-1997/Azure_Terraform/assets/32020205/fd66e570-1cce-4876-8631-97409d0c6715)

![image](https://github.com/Pavan-1997/Azure_Terraform/assets/32020205/48704f65-2535-419d-8d21-d96f42af787d)

![image](https://github.com/Pavan-1997/Azure_Terraform/assets/32020205/f84dbd09-fc3c-4615-84b4-4407fb6e577e)

![image](https://github.com/Pavan-1997/Azure_Terraform/assets/32020205/ec625ac0-74d7-4c90-beb2-0b72ec5aaab1)

---    
 
## Implementation

1. Login to Azure
```
az login 
```

2. Create a Service Princle along with a contributer role
```
az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/<ID>"
```
  If getting any error then set below enviroment variable
```
export SYS_NO_PATHCONV=1
```

3. Now test the values using below 
```
az login --service-principal -u "CLIENT_ID" -p "CERTIFICATE_PEM" --tenant "TENANT_ID"
```
4. Export the below enviromant variables
```
export ARM_CLIENT_ID="***"
export ARM_CLIENT_SECRET="***"
export ARM_TENANT_ID="***"
export ARM_SUBSCRIPTION_ID="***"
````

5. Alias Terraform command in the CLI
```
alias tf=terraform
```

6. Its always better to put any files other than .tf in gitignore and tfvars file as well
```
tf init
```
![AZ-TF-INIT](https://github.com/Pavan-1997/Azure_Terraform/assets/32020205/d2228328-6196-454c-85cc-774938941a19)

```
tf fmt
```
```
tf validate
```
```
tf plan
```
![AZ-TF-PLAN](https://github.com/Pavan-1997/Azure_Terraform/assets/32020205/f4096bdc-1c4e-4bfd-8b74-d5aaeb2db10b)

```
tf plan | grep "will be created"
```
![AZ-TF-PLAN1](https://github.com/Pavan-1997/Azure_Terraform/assets/32020205/51e5e9f0-12ab-476d-aa69-5eb2999ef39d)

```
tf apply or tf apply --auto-approve
```
```
tf fmt
```
```
tf destroy or tf destroy --auto-approve
```
7. Goto Storage Accounts in Azure Portal 

    Select Resource group
    
    Use a unique name to Storage account name
    
    Select a Region
    
    Select a Standard in Performance
    
    Select a Local-redundant storage (LRS)
    
    Click on Next
    
    In Data protection tab enable versioning for blobs
    
    Click on Review and Create
    
    Now the Storage Account is created
    
    Goto Containers on the left side -> Click on the + Container -> Give a name and click on Create

![STORAGE-ACCOUNT](https://github.com/Pavan-1997/Azure_Terraform/assets/32020205/5a67d62f-ae27-4f3f-acdd-935b00a10ee9)

![TF-BACKEND](https://github.com/Pavan-1997/Azure_Terraform/assets/32020205/629c8535-8e16-4b4e-9f6e-44f148d2d490)

![TF-BACKEND-SA](https://github.com/Pavan-1997/Azure_Terraform/assets/32020205/9d7b0e37-816d-459e-af6a-1540d5f67e3a)
