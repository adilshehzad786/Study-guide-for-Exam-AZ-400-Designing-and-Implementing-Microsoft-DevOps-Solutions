# Implement Infrastructure and Configuration as Code

# Working with ARM Templates

When working on the Azure platform, infrastructure is described using ARM templates. ARM
templates are written in JSON, and a skeleton template looks as follows:

```yaml
{
    "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {},
    "functions": [],
    "variables": {},
    "resources": [],
    "outputs": {}
}
```

## Parameters

The parameters section is usually near the top of the template. Before beginning deployment activities, ARM will resolve the parameter values. The resolved value is referenced whenever the parameter is found in the template by ARM.

```yaml
{
    "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {
        "environment": {
               "value": "dev"
        }

    }
}
```

and passing the value in the main ARM File

```yaml
{
    "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {
        "environment": {

            "type": "string"

        }
    },
    "functions": [],
    "variables": {},
    "resources": [],
    "outputs": {}
}
```

## Variables

The variables section is used to specify one or more values that will be used throughout the template.

```yaml
"variables": {
        "site_web_name": "[concat(parameters('p_site_prefix'), parameters('p_separator'), parameters('p_site_web_name'), parameters('p_separator'), parameters('p_environment'))]",
        "comosdb_default_name": "[concat(parameters('p_site_prefix'), parameters('p_separator'), parameters('p_comosdb_name'), parameters('p_separator'), parameters('p_environment'))]"
    }
```

## Resources

Resources are the main part of the template, where all of the resources to be created are specified.
This section is the only one that is not an object, but an array. Within that array, one or more objects of the following form are specified:

```yaml
{
    "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",

    "resources": [
        {
            "type": "Microsoft.DocumentDB/databaseAccounts",
            "kind": "MongoDB",
            "name": "[variables('comosdb_default_name')]",
            "apiVersion": "2015-04-08",
            "location": "[resourceGroup().location]",
            "tags": {
                "defaultExperience": "MongoDB"
            },
            "scale": null,
            "properties": {
                "name": "[variables('comosdb_default_name')]",
                "databaseAccountOfferType": "Standard",
                "consistencyPolicy": {
                    "defaultConsistencyLevel": "Session",
                    "maxIntervalInSeconds": 5,
                    "maxStalenessPrefix": 100
                }
            },
            "dependsOn": []
        },
        {
            "type": "Microsoft.Web/sites",
            "kind": "app",
            "name": "[variables('site_web_name')]",
            "apiVersion": "2016-08-01",
            "location": "[resourceGroup().location]",
            "properties": {
                "name": "[variables('site_web_name')]",
                "reserved": false,
                "siteConfig": {
                    "appSettings": [
                        {
                            "name": "COSMOS_DB_NAME",
                            "value":"[variables('comosdb_default_name')]"
                        },
                        {
                            "name": "COSMOS_DB_AUTH_KEY",
                            "value": "[listKeys(resourceId('Microsoft.DocumentDb/databaseAccounts', variables('comosdb_default_name')), '2015-04-08').primaryMasterKey]"
                        },
                        {
                            "name": "WEBSITE_NODE_DEFAULT_VERSION",
                            "value": "8.9.4"
                        }
                    ]
                }
            },
            "dependsOn": [
                "[concat('Microsoft.DocumentDB/databaseAccounts/', variables('comosdb_default_name'))]"
            ]
        }
    ],

    "outputs": {}
}
```

## Outputs

The next section of a template is the outputs section. Here are the keys returned to the caller of the
template.

```yaml
"outputs": {
        "web": {
                  "type": "string",
                  "value": "[variables('site_web_name')]"
                }
        }
```

The complete Files are available here to download

[azuredeploy.json](Implement%20Infrastructure%20and%20Configuration%20as%20Code%2063a232137bf1430d8f69bbabaeedf374/azuredeploy.json)

[deployment.parameters.json](Implement%20Infrastructure%20and%20Configuration%20as%20Code%2063a232137bf1430d8f69bbabaeedf374/deployment.parameters.json)

## Deployment

### Deployment using Powershell

```powershell
New-AzResourceGroupDeployment -ResourceGroupName
myResourceGroup - TemplateFile "c:\my\template.json" `
-TemplateParameterFile "c:\my\parameters.json"
```

### Deployment using Azure CLI

```bash
az group deployment create 窶途esource-group myResourceGroup
窶鍍emplate-file "c:\my\template.json" 窶菟arameters "c:\my\
parameters.json"
```

<aside>
庁 You can also deploy it using Azure DevOps Pipelines and Azure ARM Template.

</aside>

![Untitled](file://C:\Users\ashehzad\Downloads\Export-0a17bb71-5808-4332-8a1d-fd05784900a8\Implement%20Infrastructure%20and%20Configuration%20as%20Code%2063a232137bf1430d8f69bbabaeedf374\Untitled.png)

Click on Save

![Untitled](file://C:\Users\ashehzad\Downloads\Export-0a17bb71-5808-4332-8a1d-fd05784900a8\Implement%20Infrastructure%20and%20Configuration%20as%20Code%2063a232137bf1430d8f69bbabaeedf374\Untitled%201.png)

<aside>
庁 Make sure you change the web_name and database name

</aside>

The following resources will be created

![Untitled](file://C:\Users\ashehzad\Downloads\Export-0a17bb71-5808-4332-8a1d-fd05784900a8\Implement%20Infrastructure%20and%20Configuration%20as%20Code%2063a232137bf1430d8f69bbabaeedf374\Untitled%202.png)

# Bicep

Bicep is a Domain-Specific Language (DSL) that allows the declarative deployment of Azure resources. Everything you can do with an ARM template can be accomplished with Bicep as well.Bicep provides all resource types and API versions. Bicep provides a better authoring experience as
it supports type safety and simple declarative syntax. Bicep files are idempotent, and one file will represent the desired state. You can then use that file to repeatedly deploy your infrastructure in a
consistent manner.

# PowerShell DSC

PowerShell DSC is a notion for specifying the configuration of servers. This configuration is stored
on a pull server, where it can be accessed by one or more virtual machines.

```powershell
configuration ServerFarmConfig
{
 Node FrontEndServer

 {
 WindowsFeature IIS
 {
 Ensure = 'Present'
 Name = 'Web-Server'
 IncludeAllSubFeature = $true
 }
 File LogDirectory
 {
 Type = 'Directory'
 DestinationPath = 'C:\logs'
 Ensure = "Present"
 }
 }
}
```

# Other Tools

- CloudFormation
- Chef
- Puppet
- Terraform

# Azure Artifact & Feed

[What are feeds? - Azure Artifacts](https://learn.microsoft.com/en-us/azure/devops/artifacts/concepts/feeds?view=azure-devops)

# More Resources on DSC

[AZ-400: Manage infrastructure as code using Azure and DSC - Training](https://learn.microsoft.com/en-us/training/paths/az-400-manage-infrastructure-as-code-using-azure/)