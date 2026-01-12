# Flare

## Solution Information

| | |
|------------------------|-------|
| **Publisher** | Flare |
| **Support Tier** | Partner |
| **Support Link** | [https://flare.io/contact/](https://flare.io/contact/) |
| **Categories** | domains |
| **First Published** | 2021-10-20 |
| **Solution Folder** | [https://github.com/Azure/Azure-Sentinel/blob/master/Solutions/Flare](https://github.com/Azure/Azure-Sentinel/blob/master/Solutions/Flare) |

## Data Connectors

This solution provides **1 data connector(s)**.

### [Flare Push Connector](../connectors/fireworkpush.md)

**Publisher:** Flare Systems

The [Flare](https://flare.io) connector provides the capability to ingest threat intelligence and exposure data from Flare into Microsoft Sentinel. Flare identifies your company's digital assets made publicly available due to human error or malicious attacks, including leaked credentials, exposed cloud buckets, darkweb mentions, and more.

**Permissions:**

**Resource Provider Permissions:**
- **Workspace** (Workspace): read and write permissions are required.

**Custom Permissions:**
- **Microsoft Entra**: Permission to create an app registration in Microsoft Entra ID.
- **Microsoft Azure**: Permission to assign Monitoring Metrics Publisher role on data collection rule (DCR).
- **Flare**: Permission to configure Microsoft Sentinel integration in Flare.

**Setup Instructions:**

> ⚠️ **Note**: These instructions were automatically generated from the connector's user interface definition file using AI and may not be fully accurate. Please verify all configuration steps in the Microsoft Sentinel portal.

**1. Create ARM Resources and Provide the Required Permissions**

This connector enables Flare to send threat exposure data to Microsoft Sentinel. When data forwarding is enabled in Flare, raw event data is sent securely to the Microsoft Sentinel Ingestion API.
#### Automated Configuration and Secure Data Ingestion with Entra Application 
Clicking on "Deploy" will create Log Analytics tables and a Data Collection Rule (DCR). It will then create an Entra application, link the DCR to it, and set the entered secret in the application. This setup enables data to be sent securely to the DCR using an Entra token.
Deploy Flare connector resources

**2. Configure Flare to Send Logs to Microsoft Sentinel**

Use the following parameters to configure Flare to send logs to your workspace.
- **Entra App Registration Application ID**: `ApplicationId`
  > *Note: The value above is dynamically provided when these instructions are presented within Microsoft Sentinel.*
- **Tenant ID (Directory ID)**: `TenantId`
  > *Note: The value above is dynamically provided when these instructions are presented within Microsoft Sentinel.*
- **Entra App Registration Secret**: `ApplicationSecret`
  > *Note: The value above is dynamically provided when these instructions are presented within Microsoft Sentinel.*
- **Log Ingestion URL**: `{0}/dataCollectionRules/{1}/streams/Custom-FireworkEventsStream?api-version=2023-01-01`

**3. Configure Alert Channel in Flare**

As an organization administrator, authenticate on [Flare](https://app.flare.io) and access the [alerts page](https://app.flare.io/#/alerts?activeTab=alert-channels) to create a new alert channel. Select 'Microsoft Sentinel' and copy the above fields in the form. For more details, refer to the [Flare documentation](https://docs.flare.io).

| | |
|--------------------------|---|
| **Tables Ingested** | `FireworkV2_CL` |
| **Connector Definition Files** | [FlareFireworkEventLogs_connectorDefinition.json](https://github.com/Azure/Azure-Sentinel/blob/master/Solutions/Flare/Data%20Connectors/FlareFireworkEventLogs_ccp/FlareFireworkEventLogs_connectorDefinition.json) |

[→ View full connector details](../connectors/fireworkpush.md)

## Tables Reference

This solution ingests data into **1 table(s)**:

| Table | Used By Connectors |
|-------|-------------------|
| `FireworkV2_CL` | [Flare Push Connector](../connectors/fireworkpush.md) |

[← Back to Solutions Index](../solutions-index.md)
