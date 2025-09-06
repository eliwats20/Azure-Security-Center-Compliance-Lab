## Overview
This lab simulates a real-world sysadmin workflow using Microsoft Defender for Cloud to assess and improve the security posture of an Azure VM. It demonstrates secure deployment, NSG hardening, guest configuration, and compliance reporting — all within the free tier.

# Lab Goals
- Deploy a Windows Server VM with secure access
- Enable Defender for Cloud (CSPM)
- Review and remediate security recommendations
- Export Secure Score and compliance posture
- Document results

## Components
- **Resource Group**: `SecurityLab-RG`
- **VM**: `SecurityLab-VM` (B1s, Windows Server 2022)
- **NSG**: RDP allowed only from my IP
- **Managed Identity**: Enabled for secure access
- **Storage Account**: For boot diagnostics
- **Defender for Cloud**: CSPM enabled (free tier)

## Screenshots
| Before Remediation | After Remediation |
|--------------------|-------------------|
| ![Secure Score Before](images/secure-score-before.png) | ![Secure Score After](images/secure-score-after.png) |
