# Implementing Continuous Deployment and Release Management

URL: https://github.com/adilshehzad786/ContosoAir

# Continuous Delivery vs Continuous Deployment

Continuous delivery is a practice where teams ensure that the artifacts they build are continuously
validated and ready to be deployed to a production environment. Often, this is done by deploying the artifacts to a production-like environment, such as acceptance or even a staging environment, and applying a series of tests, such as verification tests, to ensure that an application is working correctly.

Continuous deployment is a practice where every version that is deployed to a production-like
environment and passes all tests and verifications is also deployed to production automatically.

# Lab Section 2 : Deployment

In the last section, we continuously integrate our application code and save the artifact file , now we will deploy the artifact to the Azure App Service.

1. Click on **Releases**
![Untitled](https://user-images.githubusercontent.com/53600644/210173776-8dd1202f-5bc4-4e4b-986b-d01e45d12e96.png)



1. From Release create a new Empty Release

![Untitled 1](https://user-images.githubusercontent.com/53600644/210173782-ecb9b173-5751-47fb-b015-d562709dcbc3.png)


1. Click the **Triggers** button on the artifact.
2. **Enable** continuous deployment, if it is not already enabled.
3. Now click on 1 job,0 task, and then go to variables to add pipeline variables

![Untitled 2](https://user-images.githubusercontent.com/53600644/210173786-3ad0f83d-a130-4d7f-a79d-d711144fee71.png)


1. Now go to the Azure Portal and create a resource group and then **Add** a **resourcegroup**
   variable that is not currently used by an existing resource group in your Azure account.
2. Go to Pipeline and click on Agent and then add a ARM template.
3. Fill all the details like the subscription and resource group , then linked the ARM template by clicking on the three button

![Untitled 3](https://user-images.githubusercontent.com/53600644/210173790-2ded94da-748b-4f7c-bc5a-95e6a7daafcf.png)


You will also need to set **Override template parameters** to generate an Azure app service name that is globally unique, so your name is recommended. For Example **-p_environment dev**

1. Click the **Add task** button.
  
2. Search for **“arm”** and add **ARM outputs** task. in the Resource group assign this value as we already set in variables : $(resourcegroup)
  
3. Click the **Add task** button.
  
  Search for **“app service”** and **Add** an **Azure App Service Deploy** task.
  
4. Select the newly created task.
  
5. Select the same subscription as earlier.
  
6. Enter the **App Service name** of **”$(web)”**.
  
7. **Save** the pipeline.
  
8. Note that it will take a few minutes (around 5 at the time of drafting) for the app to finish deploying due to heavy first-time operations.)
  
![Untitled 4](https://user-images.githubusercontent.com/53600644/210173793-6a523f25-b21e-4a3c-92ac-4beafa9ad2f8.png)



# Stage triggers, approvals, and gates

In Azure DevOps, a stage represents a phase in a pipeline. A pipeline is a workflow of tasks that are defined to build, test, and deploy software. You can define multiple stages in a pipeline to represent different phases of your workflow, such as build, test, and deploy.

**Triggers** in Azure DevOps allow you to automatically start a pipeline when certain conditions are met. For example, you can configure a pipeline to automatically start when a commit is made to the repository, or when a work item is created or updated.

**Approvals** allow you to review and control the deployment of your code. You can configure a stage in a pipeline to require one or more approvals before it can be run. This can be useful for ensuring that changes are reviewed and tested before they are deployed to production environments.

**Gates** in Azure DevOps allow you to automatically monitor the quality of your code and infrastructure. You can configure a stage in a pipeline to include one or more gates, which are automated checks that are performed before the stage can be run. For example, you can configure a gate to check the status of a deployment to a test environment, or to check the results of a load test. If the gate fails, the stage will not run and the pipeline will be paused until the issue is resolved.

In summary, stage triggers, approvals, and gates in Azure DevOps allow you to automate and control the workflow of your pipeline, ensuring that your code is tested and deployed in a controlled and reliable manner.

# Deployment Groups

In Azure DevOps, deployment groups are used to define the target environments for your deployments. A deployment group represents a set of machines that are used to deploy your application. You can use deployment groups to represent different environments, such as test, staging, and production.

Deployment groups are used in conjunction with release pipelines, which are used to automate the deployment of your applications. When you create a release pipeline, you can specify one or more deployment groups as the target for your deployment. The tasks in your release pipeline will be executed on the machines in the deployment group.

Deployment groups are useful for deploying your application to multiple environments or to multiple target machines. They allow you to define a set of machines that can be used to deploy your application, and you can specify different deployment groups for different environments. This makes it easier to manage and control your deployments, and helps ensure that your application is deployed consistently across different environments.

## Managing deployment groups

Before you can add a deployment group job to a release pipeline, you need to create a deployment
group. To do so, perform the following steps:

1. Navigate to the Pipelines menu.
2. Open the Deployment groups menu.
3. Click on New to add a new deployment group.
4. Enter a deployment group name and description and click Create

# Deployment Strategy

## Blue/Green Deployment

Blue/green deployment involves deploying a new version of your application to a separate environment and then switching traffic between the old and new environments. The old environment is referred to as the "blue" environment, and the new environment is referred to as the "green" environment. This allows you to test the new version of your application in a live environment without disrupting the existing production environment. Once you have tested and validated the new version of your application, you can switch traffic to the green environment, effectively replacing the old version of your application with the new version.

## Canary Deployment

Canary deployment is a similar technique that involves deploying a new version of your application to a small subset of users or machines, and gradually rolling out the new version to more users or machines over time. This allows you to test and validate the new version of your application in a live environment with a small group of users, before rolling it out to the entire user base. Canary deployment can help reduce the risk of issues and downtime, and it can also allow you to gather feedback from users before rolling out the new version to everyone.

# More Resources

[AZ-400: Design and implement a release strategy - Training](https://learn.microsoft.com/en-us/training/paths/az-400-design-implement-release-strategy/)
