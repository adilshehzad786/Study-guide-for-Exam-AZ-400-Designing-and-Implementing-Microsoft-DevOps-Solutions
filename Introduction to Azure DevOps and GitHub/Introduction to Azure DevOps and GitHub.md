# Introduction to Azure DevOps and GitHub


# What is Azure DevOps

Azure DevOps is a set of development tools, services, and features that enable teams to plan, develop, deliver, and maintain software more efficiently. It includes a range of services, such as Azure Boards, Azure Repos, Azure Pipelines, Azure Test Plans, and Azure Artifacts, that work together to help teams manage the complete development process.

## Azure Board

Azure Board is a work-tracking system that provides customizable dashboards, reporting, and tracking tools to help teams track and prioritize work, defects, and issues.

![Untitled](https://user-images.githubusercontent.com/53600644/210172441-ca90f4ab-71c9-4855-9a02-925730f62f63.png)


## Azure Repo

Azure Repos is a version control system that allows teams to track code changes and collaborate on code development.

Azure Repos offers two types of version control systems:
**Team Foundation Version Control (TFVC):** This is a centralized version control system. Though not widely used in recent times, many project teams are continuing to use this approach for legacy purposes only.
**Git:** This is the more popular distributed version control system. If you are just starting your
DevOps journey, it is recommended to start with a Git-based version control system only.
![Untitled 1](https://user-images.githubusercontent.com/53600644/210172447-92eecb77-4f9a-4e05-9e3f-b14f765586b7.png)



## Azure Pipeline

Azure Pipelines is a continuous integration and delivery (CI/CD) platform that helps teams automate the build, test, and deployment of their applications.

![Untitled 2](https://user-images.githubusercontent.com/53600644/210172451-8a0831c7-c945-4076-856d-7530fcc14ae7.png)


## Azure Test Plans

Azure Test Plans is a testing tool that helps teams plan, track, and manage their testing efforts.


![Untitled 3](https://user-images.githubusercontent.com/53600644/210172455-75e325a2-1766-4180-bf89-2cfc8d1adc4a.png)

## Azure Artifacts

Azure Artifacts is a package management service that enables teams to share Maven, npm, and NuGet packages. In Azure Artifacts, a feed is a container for packages. It is a way to organize and manage packages that are used by your team or organization. A feed can be created within a project or as a standalone entity, and it can be public or private.

![Untitled 4](https://user-images.githubusercontent.com/53600644/210172457-806d66a5-f317-41f7-a5f4-15f1b44aef79.png)


# What is GitHub?

GitHub is a web-based platform that provides hosting for software development version control using Git. GitHub offers a range of features and tools that make it easier for developers to collaborate on software projects. These include version control, bug tracking, project management, and code review tools. GitHub is widely used by individual developers, open-source projects, and organizations of all sizes.

# Azure Monitor

Azure Monitor provides rich dashboarding capabilities to help you monitor application-specific
metrics, resource health, and utilization to detect anomalies and provide timely intervention.

Some of the features :
• **Log Analytics** for digging into the monitoring data and deriving deep insights
• **Application Insight**s for end-to-end transaction traceability, exceptions, and performance metrics
• **Container Insights** for microservices usage and health-related statistics
• **Custom dashboards** that are tailored to the use cases to track usage and reliability metrics
• **Alerts** to detect anomalies and notify teams about the appropriate action, as well as executing
automated actions

# Learning Table


|Activity|Tool  |
|--|--|
| Manage your product backlog Plan and track your work Prepare dashboard and report |  Azure Boards|
| Develop code locally | Develop code locally |
| Manage and track changes to your source code | Azure Repos ,Git |
| CI/CD | Azure Pipelines GitHub Actions Jenkins |
| Provision developer environment | Provision developer environment |
| Infrastructure as Code | ARM (Azure Resource Manager) Azure CLI Ansible and Terraform |
| Manage the configuration of your resources | Ansible, Terraform, Chef , Puppet and Azure Automation. |
| Advance Analytics and reporting | Power BI |
| Capture and analyze logs| Azure Monitor and Data Explorer |
| Prepare test plans and manage execution| Azure test Plans |
| Azure test Plans| Azure Artifacts|
| Improve productivity by using third-party extensions and plugins.| Azure DevOps Marketplace GitHub Marketplace|






