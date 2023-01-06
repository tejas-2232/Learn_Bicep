

__The following four Azure resources are created by this Bicep file:__

* Microsoft.Storage/storageAccounts: create an Azure Storage account, which is required by Functions.
* Microsoft.Web/serverfarms: create a serverless Consumption hosting plan for the function app.
* Microsoft.Web/sites: create a function app.
* microsoft.insights/components: create an Application Insights instance for monitoring.

<hr>

## Deploy the Bicep file

* Save the Bicep file as main.bicep to your local computer.
* Deploy the Bicep file using either Azure CLI.

```sh
az group create --name exampleRG --location eastus
az deployment group create --resource-group exampleRG --template-file main.bicep --parameters appInsightsLocation=<app-location>
```

__Note:__
Replace <*app-location*> with the region for Application Insights, which is usually the same as the resource group.

* When the deployment finishes, you should see a message indicating the deployment succeeded.


## Validate the deployment

```
az resource list --resource-group exampleRG
```

## Visit function app welcome page

1. Use the output from the previous validation step to retrieve the unique name created for your function app.

2. Open a browser and enter the following URL: <https://<appName.azurewebsites.net>. 
 <br>Make sure to replace <\appName> with the unique name created for your function app.

When you visit the URL, you should see a page like this:

![image](https://learn.microsoft.com/en-us/azure/azure-functions/media/functions-create-first-function-bicep/function-app-bicep.png)

<hr>

## Clean up resources

```
az group delete --name exampleRG
```
