# Introduction to SRE

# What is SRE?

Site Reliability Engineering (SRE) is a discipline that focuses on the reliability, performance, and availability of software systems. It involves proactively identifying and addressing potential issues to minimize downtime and maximize uptime. SRE teams are responsible for the design, development, and operation of software systems and work closely with software developers to ensure that systems meet the needs of the business and its customers. SRE principles can be applied to a wide range of software systems, including web applications, mobile apps, and backend systems.

> The term SRE was first coined by Ben Treynor Sloss at Google ([https://sre.google/sre-book/](https://sre.google/sre-book/)
> introduction/). SRE has enabled Google to manage large-sized complex systems and massive
> infrastructure in the most efficient, reliable, scalable, and sustainable way

## What is Availability?

The availability of the systems can be measured as the percentage of time in which the system is
available or fully operational.

Formula to measure the availability of Application

<aside>
💡 Availability % = ((Service Uptime - Service Downtime) ÷ (Service Uptime)) * 100

</aside>

## Hierarchy of Service Reliability (From down to Top )

- Monitoring
- Incident purpose
- Post modern/root cause analysis
- Testing + Release procedure
- Capacity Planning
- Development Product

## SLO

Service-level objectives (SLOs) are targets that a service provider sets for the performance of a service. SLOs are typically defined in terms of metrics such as availability, response time, and error rate.

## SLI

Service-level indicators (SLIs) are metrics that are used to measure the performance of a service against the service-level objectives. SLIs are used to track the performance of a service over time and to identify any issues or trends that may need to be addressed.

## TOIL

Toil is a term used in the field of site reliability engineering (SRE) to refer to tasks that are manual, repetitive, automatable, tactical, and devoid of lasting value. Toil can include tasks such as monitoring alerts, restarting failed services, and applying patches to systems.

# Resources

- Google’s SRE book: [https://sre.google/sre-book/part-I-introduction/](https://sre.google/sre-book/part-I-introduction/)
  • Microsoft’s SRE documentation: [https://docs.microsoft.com/en-us/learn/modules/intro-to-site-reliability-engineering](https://docs.microsoft.com/en-us/learn/modules/intro-to-site-reliability-engineering?wt.mc_id=studentamb_159507)/
  • Azure Monitor: [https://docs.microsoft.com/en-us/azure/azure-monitor/](https://docs.microsoft.com/en-us/azure/azure-monitor/?wt.mc_id=studentamb_159507)
  overview
  • Azure Application Insights: [https://docs.microsoft.com/en-us/azure/azuremonitor/app/app-insights-overview](https://docs.microsoft.com/en-us/azure/azuremonitor/app/app-insights-overview?wt.mc_id=studentamb_159507)
  • Azure Automation: [https://docs.microsoft.com/en-us/azure/automation/](https://docs.microsoft.com/en-us/azure/automation/?wt.mc_id=studentamb_159507)
  overview

[Introduction to Azure DevOps and GitHub](https://www.notion.so/Introduction-to-Azure-DevOps-and-GitHub-49fd655ca5734671b0422c39055157b9)
