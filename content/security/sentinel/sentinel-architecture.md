# Microsoft Sentinel Architecture and Workspace design

## Overview

In this session, we will cover how to approach Workspace design when implementing Microsoft Sentinel, considering concepts like multi-tenancy, charge back, complex permissions and more.
We will also look at additional things to consider when designing your Microsoft Sentinel implementation

## Agenda

1. Overview of Workspace Requirements
2. Considerations for one or multiple workspaces
3. Additional considerations for workspace design
4. Additional considerations for Sentinel implementations.


## Session Summary

### Workspace Design Considerations

* Microsoft Sentinel uses an Azure Monitor Logs workspace as its data store
* There is a one to one relationship between a Microsoft Sentinel instance and the workspace
* Considerations for one or multiple workspaces
    * Do you have existing workspaces in place?
    * Are any of your existing workspaces already collecting security-related logs, such as audit logs from Entra ID (AAD) or applications, or Security logs from Windows servers?
    * Are you also using Azure Monitor today?
    * Do you have multiple tenants? Do they each have an Office 365 environment?
    * Do you have requirements for charge back or split billing?
    * Do you have any regulatory or legal requirements to segregate the security data, or retain security data in a specific region?


### Additional considerations for Sentinel implementations

* If you are planning on collecting logs from network or security devices outside of Azure, you will often require a Syslog server for log collection
* To collect logs from the servers in Azure, you will need to deploy the Azure Monitor Agent. This can be done by adding the servers to a data collection rule.
* To collect logs from servers outside of Azure, you will need to deploy the Azure Arc agent first, and then the Azure Monitor Agent.
* If you would like to collect security logs from Windows Servers and client devices without deployment of an agent, you can use Windows Event Forwarding. This will require a Windows Event Collector server to be deployed



## Additional Resources

* [Design your Microsoft Sentinel workspace architecture](https://learn.microsoft.com/en-us/azure/sentinel/design-your-workspace-architecture)
* [Geographical availability and data residency in Microsoft Sentinel](https://learn.microsoft.com/en-us/azure/sentinel/geographical-availability-data-residency)
* [Manage access to Microsoft Sentinel data by resource](https://learn.microsoft.com/en-us/azure/sentinel/resource-context-rbac)
* [Windows Security Events via AMA connector for Microsoft Sentinel](https://review.learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-linux?view=o365-worldwide&branch=main#installation-instructions)
* [What is Azure Arc-enabled servers?](https://learn.microsoft.com/en-us/azure/azure-arc/servers/overview)
