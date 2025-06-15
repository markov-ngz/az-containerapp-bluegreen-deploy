# Blue/Green Deployment on Azure Container App 
Automate your blue-green deployments for Azure Container Apps from your Github Actions workflows.

## How to use this action ? 
1. Login to Azure
```
- name: Azure login
  uses: azure/login@v2 # choose latest version 
  with:
    client-id: ${{ secrets.AZURE_CLIENT_ID }}
    tenant-id: ${{ secrets.AZURE_TENANT_ID }}
    subscription-id: ${{ secrets.AZURE_SUBSCRIPTION_ID }}
```

2. Use the action
```
- name: Deploy to Azure Container App 
  uses: markov-ngz/containerapp-bluegreen-deploy@v1.0.0 # choose the right deployment tag
  with:
      resource_group_name: <resource groupe name>
      container_app_name: <name of the container app>
      image_full_name: < image full name> # example :  <registry_name>.azurecr.io/<image_name>:<image_tag> , not necessary for public docker repositories ( ex : nginx:latest  works )
```
It will create new revision with a tag named "blue" or "green" and direct ingress traffic to it.

## Cite and share
If you found it useful, don't forget to add a star to the repository 😊 
