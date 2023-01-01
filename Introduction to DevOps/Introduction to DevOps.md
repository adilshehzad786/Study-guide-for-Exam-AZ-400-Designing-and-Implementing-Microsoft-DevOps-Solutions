# Introduction to DevOps

# What is DevOps?

DevOps is a way of working that helps development and operations teams collaborate more effectively to deliver software quickly and reliably. It involves automating processes and using agile and SRE principles to improve team collaboration and communication.

In Traditional organizations, developers and operations are often located in different departments, and taking software into production includes a hand-off, often with a formal ceremony around it. In such an organization, it can be hard to accelerate that delivery to production along with the speed at which development can create a new version

Next to that the development and operations departments often have conflicting goals. While a development department is rewarded for creating many changes as quickly as possible, operating departments are rewarded for limiting downtime and preventing issues.

> *A very good read is The Phoenix Project: A Novel About IT, DevOps, And Helping Your Business Win, by Gene Kim.*

## Agile

Agile work management is a flexible approach to planning and guiding project work that emphasizes the importance of responding to change and frequent collaboration. It involves breaking projects down into small cycles (called "sprints") and regularly reviewing and adjusting the plan based on feedback and progress.

**User Stores → Agile**

## Scrum

Scrum is a framework for agile software development that helps teams deliver software quickly and iteratively. It involves breaking work down into short cycles (called "sprints") during which specific tasks are completed and deliverables are produced. A team works together to plan, execute, and review each sprint and is responsible for delivering a potentially shippable product increment at the end of each sprint.

# Creating your DevOps Organization

To create an organization in Azure DevOps, follow these steps:

1. Go to the Azure DevOps website (**[https://dev.azure.com/](https://dev.azure.com/)**).
2. Click on the "Sign up for free" button.
3. Enter your email address and create a password.
4. Click on the "Continue" button.
5. Follow the on-screen instructions to complete the sign-up process.

Once you have signed up for Azure DevOps, you can create a new organization by following these steps:

1. Go to the Azure DevOps homepage and click on the "Create organization" button.
2. Enter a name for your organization and choose a region.
3. Click on the "Create" button.

Your new organization will be created, and you will be taken to the organization dashboard. From here, you can create and manage projects, collaborate with team members, and track work progress.

![Untitled](https://user-images.githubusercontent.com/53600644/210171462-1ce5feb3-d197-49ef-999b-04b2ad88e617.png)



# Exploring DevOps Practices

## Configuration Management

Configuration management is about versioning the configuration of your application and the components it relies on, along with your application itself. Tools such as Ansible, Terraform, puppet, or PowerShell DSC configure your environment and application.

## Release Management

Release Management is about being in control of which version of your software is deployed to which environment. Versions are often created using continuous integration and delivery pipelines.

## Continuous Integration

Continuous Integration is a practice where every developer integrates their work with that of the other developers in the team at least once a day and preferably more often. This means that every developer should push their work to the repository at least once a day. A Continuous Integration build verifies that their work compiles and that all the unit tests run.

## Continuous Deployment

Continuous Deployment is a practice of automatically deploying every new version of sufficient quality to production. When practicing continuous deployment, you have fully automated pipeline that takes in every new version of your application (every commit) , results in a new release and start deploying it to one or more enviornment. The first environment is often called test and the final environment is called production.

[Continuous delivery - Wikipedia](https://en.wikipedia.org/wiki/Continuous_delivery#/media/File:Continuous_Delivery_process_diagram.svg)

## Infrastructure as Code

Infrastructure as code (IaC) is the practice of managing and provisioning infrastructure using code, rather than manual processes. It allows organizations to define and manage their infrastructure in a declarative way and automate the process of provisioning and managing infrastructure resources. This can improve efficiency, reduce errors, and increase the speed of deployment. When the time comes to release a new version of the application and you need to make one or more changes to the infrastructure, you are executing this description of your desired infrastructure using tools such as Chef, Puppet, Terraform, Azure Bicep, PowerShell DSC, or Azure ARM templates

## Test Automation

To continuously deliver values to your end user you must release fast and often. you will most likely want to create multiple test suites for the application that you run at different stages of your delivery pipeline. Fast unit tests that run within a few minutes and that are executed whenever a new pull request is opened should give your team very quick feedback on the quality of their work and it should catch most of the errors.

## Application Performance Monitoring

This last practice is all about learning how your application is doing in production. Gathering metrics such as response times and the number of requests will tell you about how the systems are performing. Capturing errors is also part of performance monitoring and allows you to start fixing problems without having to wait on your customers to contact you about them.

# Resources

[Introduction to DevOps - Training](https://learn.microsoft.com/en-us/training/modules/introduction-to-devops/?ns-enrollment-type=learningpath&ns-enrollment-id=learn.wwl.az-400-get-started-devops-transformation-journey)

