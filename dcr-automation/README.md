# DCR Automation Config Files

Configuration files for deploying Azure Monitor Data Collection Rules (DCRs) for the 9 AWS native Sentinel tables using the [criblio/Cribl-Microsoft](https://github.com/criblio/Cribl-Microsoft) DCR automation scripts.

## Prerequisites

1. Clone `criblio/Cribl-Microsoft` and navigate to:
   ```
   Azure/CustomDeploymentTemplates/DCR-Automation/
   ```

2. Install the Az PowerShell module and authenticate:
   ```powershell
   Install-Module Az -Scope CurrentUser
   Connect-AzAccount
   ```

## Setup

Copy the 4 config files from this folder into the `core/` directory of the DCR-Automation scripts:

```
cp NativeTableList.json    <path-to>/DCR-Automation/core/
cp azure-parameters.json   <path-to>/DCR-Automation/core/
cp cribl-parameters.json   <path-to>/DCR-Automation/core/
cp operation-parameters.json <path-to>/DCR-Automation/core/
```

Fill in the placeholder values in `azure-parameters.json` before running:

| Field | Where to find it |
|---|---|
| `subscriptionId` | Azure Portal → Subscriptions |
| `resourceGroupName` | Target RG for DCRs |
| `workspaceName` | Log Analytics workspace name |
| `location` | Azure region (e.g., `eastus`) |
| `tenantId` | Azure AD → Overview |
| `clientId` | Azure AD → App registrations → your app |

## Run

```powershell
cd <path-to>/DCR-Automation
.\Run-DCRAutomation.ps1 -NonInteractive -Mode DirectNative
```

This deploys Direct DCRs (no DCE required) for all 9 AWS tables in `NativeTableList.json`. Output includes ARM templates, deployed DCRs, and ready-to-import Cribl destination configs in `core/cribl-dcr-configs/`.

## Tables Deployed

- AWSCloudTrail
- AWSVPCFlow
- AWSGuardDuty
- AWSWAF
- AWSRoute53Resolver
- AWSALBAccessLogs
- AWSNLBAccessLogs
- AWSS3ServerAccess
- AWSSecurityHubFindings

## DCR Naming

DCRs are named `dcr-{TableName}-aws` (e.g., `dcr-AWSCloudTrail-aws`).
Cribl destination IDs are named `sentinel-{TableName}` (e.g., `sentinel-AWSCloudTrail`).
