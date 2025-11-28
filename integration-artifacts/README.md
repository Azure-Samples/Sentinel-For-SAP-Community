# Available integration scenarios

| **Recipe** | **Description** | **Package** | **Provided by** |
| --- | --- | --- | --- |
| SAP Ariba (preview) | This flow supports integration with [SAP Ariba Audit Search API](https://api.sap.com/api/audit_search_v2/overview) to extract audit logs for Sentinel ingestion.| 🔗[link](solution-packages/baseline-extension-package/) | [MartinPankraz](https://github.com/MartinPankraz/) |
| SAP S/4HANA Cloud Public Edition (GROW) | This flow supports integration with SAP S/4HANA Cloud Public Edition using communication scenario [SAP_COM_0750](https://help.sap.com/docs/SAP_S4HANA_CLOUD/0f69f8fb28ac4bf48d2b57b9637e81fa/a93dca70e2ce43d19ac93e3e5531e37d.html) | 🔗[link](solution-packages/baseline-extension-package/) | [MartinPankraz](https://github.com/MartinPankraz/) |
| SOAR for SAP | This flow supports the [Sentinel for SAP SOAR scenarios](https://learn.microsoft.com/azure/sentinel/sap/sap-solution-security-content#available-playbooks) via SAP Integration Suite: SAP User blocking via Microsoft Teams and automatic SAP audit log re-activation | 🔗[link](solution-packages/baseline-extension-package/) | [MartinPankraz](https://github.com/MartinPankraz/) |
| SAP Table Reader | This flow supports reading of tables on AS ABAP via RFC_READ_TABLE interface. Target custom log table in Sentinel needs to be [created manually](https://learn.microsoft.com/azure/azure-monitor/logs/create-custom-table?tabs=azure-portal-1%2Cazure-portal-2%2Cazure-portal-3) beforehand | 🔗[link](solution-packages/baseline-extension-package/) | [MartinPankraz](https://github.com/MartinPankraz/) |

Contribute your own integration scenarios to this repository! See the [contribution guidelines](../CONTRIBUTING.md) and the [contribution packaging guide](../PACKAGING.md) for more information.

> [!TIP]
> Make sure that single iFlows are imported into existing packages. Vice versa full packages need to be imported on the top level screen.

## How to install from source

1. Download the latest [solution](solution-packages/) by solution package (zip files in folder).
2. Import the solution package into your SAP Integration Suite.
   - Go to the **Design** tab in your SAP Integration Suite.
   - Click on **Packages** in the left navigation pane.
   - Click on **Import** and select the downloaded solution package.

3. Check the [configuration hints](solution-packages/baseline-extension-package) for your artifacts.

4. Deploy the iFlows you want to use.

> [!WARNING]
> Single iFlows can only be imported into existing packages.
