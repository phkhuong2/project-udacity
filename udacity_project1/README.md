# Udacity Azure Dev-Ops Project 1: Deploying a Web Server in Azure

This is a project related to Udacity Azure DevOps nanodegree.
In this project, you will write a Packer template and a Terraform template to deploy a customizable, scalable web server in Azure

## Dependencies

- Create an [Azure Account](https://portal.azure.com) 
- Install the [Azure command line interface (Azure CLI )](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)
- Install [Packer](https://www.packer.io/downloads)
- Install [Terraform](https://www.terraform.io/downloads.html)

## Deploy

### Export the variable

Add to your .bashrc (or .zshrc) file:

```
export AZ_CLIENT_ID=00000000-0000-0000-0000-000000000000
export AZ_CLIENT_SECRET=000000000000000000000
export AZ_TENANT_ID=00000000-0000-0000-0000-000000000000
export AZ_SUSCRIPTION_ID=00000000-0000-0000-0000-000000000000
```

(Obviously, change the value with yours.)

### Deploy the policy

Deploy the policy (I did it on Azure Portal) and assign it to the resource group.

### Create the Packer image

```
$ packer build packer/server.json
```
![Parker_image_build](./Image/packer_build.png)
### Initialize Terraform deployment

```
$ terraform init
```
![terrform_init](./Image/tarraform_init.png)
### Terraform execution plan
- Terraform plan command creates plan
```
$ terraform plan -out solution.plan
```
![terrform_plan_out](./Image/terraform_plan_out.png)
### Deploy with Terraform

```
$ terraform apply "solution.plan"
```

## After

Destroy the infrastructure with:

```
$ terraform deploy
```
Terraform will perform:
![terraform out put](./Image/output.png)

## Modify

The file `terraform/vars.tf` contains all the variables used inside the `terraform/main.tf`. If you want to personnalize the code, it is likely those values you want to modify first.
