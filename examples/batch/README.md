## Deploy the Bicep file

Save the Bicep file as main.bicep to your local computer.

Deploy the Bicep file using either Azure CLI or Azure PowerShell.

```azurecli
az group create --name exampleRG --location eastus

az deployment group create --resource-group exampleRG --template-file main.bicep
```

* When the deployment finishes, you should see a message indicating the deployment succeeded.


## Validate the deployment

```
az resource list --resource-group exampleRG
```

## Clean up resources

```
az group delete --name exampleRG
```
