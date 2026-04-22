# Copilot Instructions for Sentinel-For-SAP-Community

## What This Repository Is

A community-driven collection of SAP Integration Suite "recipes" (integration flows/iFlows) that extend the official [Microsoft Sentinel Solution for SAP](https://learn.microsoft.com/azure/sentinel/sap/deployment-overview?tabs=agentless). The artifacts are zip packages consumed by SAP Cloud Integration tenants—not source code compiled locally.

## Repository Architecture

```
integration-artifacts/
  solution-packages/
    baseline-extension-package/    # Versioned zip packages of iFlows + README with config hints
  README.md                        # Scenario catalog table linking recipes to packages and blogs
```

- **Zip packages** under `solution-packages/baseline-extension-package/` follow the naming pattern: `Community extensions for Microsoft Sentinel Solution for SAP ERP and S_4HANA-<version>.zip`
- Each new release increments the version and is documented in `CHANGELOG.md` and the package's `README.md` release notes table.
- The repository root `README.md` provides getting started instructions; the `integration-artifacts/README.md` is the scenario catalog.

## CI / Automation

The only automated workflow is `.github/workflows/links-watcher.yml`—a daily link checker (lychee) that scans all markdown files and auto-creates/updates a GitHub issue labeled `broken link, automated issue` on failure. There are no build, test, or lint commands.

## Contributing a New Recipe

Follow the process in `PACKAGING.md`:

1. Fork the repo.
2. Create a folder under `integration-artifacts/<artifact-type>/<scenario-name>/` (use `<verb>-<object>` naming).
3. Include: iFlow zip files, sample payloads, screenshots (BPMN diagram, config screens), and a `README.md` using the template at `integration-artifacts/solution-packages/`.
4. Update `integration-artifacts/README.md` with a new row in the scenario catalog table.
5. Update `CHANGELOG.md` and the package-level release notes if modifying the baseline extension package.
6. Submit a PR—a CLA bot will prompt on first contribution.

## Key Conventions

- **Intellectual property**: Never include IP, business secrets, or references to employer/customer/partner proprietary material. All commits are public domain.
- **SAP design guidelines**: iFlows must comply with SAP's [Integration Flow Design Guidelines](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/integration-flow-design-guidelines).
- **Custom Sentinel tables**: DCR-based custom log tables use the naming convention `Custom-<name>_CL` (prefix `Custom-`, suffix `_CL`).
- **Community API paths**: Community iFlows use path prefixes like `/community/<FlowName>` (e.g., `/community/SAPAribaAuditSearch`) to coexist with official connectors.
- **KQL snippets**: Configuration docs include KQL query examples for Sentinel—preserve their formatting when editing documentation.
- **Date format**: The project uses DD-MM-YYYY in changelog and release notes tables.
