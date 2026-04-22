<div align="center">
  <img src="Gemini_Generated_Image_wy0z0dwy0z0dwy0z (2).png" alt="RopaSecurity Banner" width="100%">
</div>

1. The "Zero Trust" Automation Script
This sample showcases your skill in **Hardening Cloud Environments** and managing **Azure Active Directory**

File Name: `New-ZeroTrustUserProvisioning.ps1`
Purpose:** Automates the creation of a new user while immediately applying **custom RBAC roles** and security baselines.

powershell
<#
.SYNOPSIS
    Secure User Onboarding for Azure AD.
    Author: Rose Pavia | RosepaSecurity
#>

param (
    [Parameter(Mandatory=$true)][string]$UserPrincipalName,
    [Parameter(Mandatory=$true)][string]$DisplayName
)

1. Create the Azure AD User with a secure, temporary password
$PasswordProfile = New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password = "TempPass!2026_Secure"
New-AzureADUser -DisplayName $DisplayName -PasswordProfile $PasswordProfile -UserPrincipalName $UserPrincipalName -AccountEnabled $true

2. Assign Custom RBAC Role (Security Reader) immediately 
$Role = Get-AzRoleDefinition -Name "Security Reader"
New-AzRoleAssignment -SignInName $UserPrincipalName -RoleDefinitionName $Role.Name -Scope "/subscriptions/YourSubID"

Write-Host "User $DisplayName created and secured with RBAC Role: $($Role.Name)" -ForegroundColor Green

3. Infrastructure as Code (IaC) - The "Safe Haven" Lab
This sample proves you can configure **enterprise-level infrastructure including DNS and DHCP using code.

File Name: `Deploy-SecureHybridVNet.json` (ARM Template)
Purpose: A template that deploys a virtual network with a pre-configured **Network Security Group (NSG)** that restricts all traffic except for your specific administrative IP.

Brand Value: Highlights your 600+ hours of technical training in managing **Azure and networking resources.

Narrative: In the README, explain that you built this template to replicate the "clean room" environments you used for forensic evidence collection** and **incident triage** at Google and Amazon.

4. The "Incident Triage" Runbook (Documentation)
Since you "developed comprehensive runbooks to improve team response capabilities" at Amazon, you should host a professional **Markdown (.md)** runbook in your repo.

File Name: `RUNBOOK-Cloud-Outage-Recovery.md`
Content: A step-by-step technical guide for recovering from a major service disruption (like the **AWS DNS** or Crowdstrike outages you managed.

| Phase | Action | Technical Tool|
| :--- | :--- | :--- |
| Identification | Query logs for DNS resolution failures. | PowerShell / Azure Monitor |
| Containment | Isolate affected Virtual Machines via NSG rules. | Azure Portal / CLI |
| Recovery | Re-deploy affected resources using Bicep/ARM. | Azure Resource Manager |
| Review | Create a post-incident report for leadership. | QuickSight / Asana |


/RP-MSSA-Cloud-System-Portfolio
│
├── /Automation-Scripts
[cite_start]│   └── New-ZeroTrustUserProvisioning.ps1   # PowerShell Automator Brand [cite: 12]
├── /Cloud-Templates
[cite_start]│   └── Deploy-SecureHybridVNet.json        # Azure/MSSA Expertise [cite: 11, 23]
└── /Incident-Ops-Runbooks
    [cite_start]└── RUNBOOK-Cloud-Outage-Recovery.md    # Global Leadership Legacy [cite: 16, 38]


