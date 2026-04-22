# KQL Parsers

Custom [KQL](https://learn.microsoft.com/kusto/query) parser functions for Microsoft Sentinel for SAP log tables populated by the community integration flows.

## Available Parsers

| **Parser** | **Function Name** | **Description** |
| --- | --- | --- |
| [pahi-legacy-parser.kql](pahi-legacy-parser.kql) | `SAP_PAHI` | Unifies the agent-based `ABAP_PAHI_CL` and agentless `ABAP_PAHI_2_CL` tables into a single schema. Required by the legacy analytic rule *[Monitor the configuration of static SAP security parameters](https://learn.microsoft.com/azure/sentinel/sap/sap-suspicious-configuration-security-parameters)*. |

## How to Deploy

1. Open the **Log Analytics workspace** query editor in the Azure portal.
2. Paste the KQL from the parser file.
3. Click **Save** → **Save as function** and name it as indicated above (e.g., `SAP_PAHI`).
4. Override if a previous version exists.

Refer to the [configuration hints](../solution-packages/baseline-extension-package/) for details on table setup and prerequisites.
