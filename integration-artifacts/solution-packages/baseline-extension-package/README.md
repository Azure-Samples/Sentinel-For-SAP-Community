# Release Notes

| **Version** | **Date Modified (DD-MM-YYYY)** | **Comments** |
| --- | --- | --- |
| 1.0.2 | 30-05-2025 | SOAR - user unblock action added |
| 1.0.1 | 09-05-2025 | ABAP Table Reader scenario release |
| 1.0.0 | 17-04-2025 | SOAR for SAP scenario release |

## Configuration hints

### SAP Integration Suite endpoint and RFC destination name

There are multiple ways to retrieve the required info for the SAP Integration Suite endpoint and the RFC destination name on SAP BTP for the Sentinel [playbook](https://learn.microsoft.com/azure/sentinel/sap/sap-solution-security-content#available-playbooks). See one inline KQL query example below.

```kql
ABAPAuditLog
| where SystemId == "PM4"
| distinct SystemUniqueId, AgentId
```

### Custom Sentinel tables

DCR-based custom log tables require the target schema to be defined beforehand. Find the instructions [here](https://learn.microsoft.com/azure/azure-monitor/logs/create-custom-table?tabs=azure-portal-1%2Cazure-portal-2%2Cazure-portal-3#create-a-custom-table).

- Get sample json payload for schema generation for your custom SAP table in Sentinel by executing the table reader iFlow.

- Configure the iflow using the newly created Data Collection Endpoint, immutable id of the associated data collection rule, and your custom table name (log analytics stream name). It will look something like this: "Custom-test_rfc_CL". Prefix "Custom-" and suffix "_CL" are required.

- Conclude the exercise by providing access to your data collection rule with role "Monitoring Metrics Publisher" to a service principal. See instructions and prerequisites [here](https://learn.microsoft.com/entra/identity-platform/howto-create-service-principal-portal#option-3-create-a-new-client-secret).

- Now, Run your iFlow to send data to Sentinel.

> [!NOTE]
> Log Analytics creates a TimeGenerated field if none is provided and treats all incoming values as append log stream. Meaning re-runs of the iFlow will create duplicates. Manage that by using only latest timestamp in Sentinel or altering the iFlow to do change data capture before posting.

### Permissions

| **flow** | **Relevant SAP permissions** | **Comments** |
| --- | --- | --- |
| SAP User Block from Microsoft Teams | BAPI_USER_LOCK, BAPI_USER_UNLOCK, TH_DELETE_USER | RFCs to be allowed on SAP Cloud Connector |
| SAP Table Reader | RFC_READ_TABLE | RFC Already allowed as part of official Sentinel for SAP agentless package |
| SAP AS JAVA log collector | SAPControl user | Deploy SAP's Azure Adapter for SAP Integration Suite prior |
