# AZURE-TERRAFORM-LEARNINGS
# to create subscription id , client id , client secret, tennat id --> peform the follwoing steps and upload it in terraform.tfvars


az login
az account show --query id -o tsv
az account show --query tenantId -o tsv
az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/<your_subscription_id>"


Replace <your_subscription_id> with the actual subscription ID obtained in command 2.

This command will output:

appId (which is the client_id)
password (which is the client_secret)
tenant (which is the tenant_id you got in command 3)