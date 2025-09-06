## 📄 Remediation Summary

| Category                  | Action Taken                                               | Status     | Notes                                                                 |
|---------------------------|-------------------------------------------------------------|------------|-----------------------------------------------------------------------|
| Guest Configuration       | Installed Azure Machine Configuration extension             | ✅ Done     | Enabled OS-level compliance scanning                                 |
| Diagnostic Settings       | Enabled logging to Storage Account (`eliyahsa`)             | ✅ Done     | 5 GB quota, Error-level logs, Blob storage only                      |
| NSG Hardening             | Restricted inbound RDP/SSH to specific IP                   | ✅ Done     | Removed `0.0.0.0/0` exposure                                         |
| Defender for Servers      | **Not enabled**                                             | ❌ Skipped  | Paid feature; excluded to maintain free-tier compliance              |
| Defender CSPM             | **Not enabled**                                             | ❌ Skipped  | Avoided $5/resource/month charge                                     |
| Secure Score              | Initial score 0%; posture checks pending                    | ⏳ Pending | Most items marked “Not evaluated”; expected to update within 24 hrs  |
| Compliance Benchmark      | Microsoft Cloud Security Benchmark (MCSB) active            | ✅ Done     | 57 of 63 controls passed                                             |
| RDP Access Issue          | Unable to connect via public IP; worked over VNet only      | ⚠️ Observed | Likely caused by NSG restrictions or missing public IP configuration |

## 🔍 Additional Notes

- **Guest Configuration** was installed via the Azure Portal using the “Azure Machine Configuration extension for Windows” published by Microsoft Corporation.
- **Diagnostic settings** were configured to send logs to a Blob Storage account (`eliyahsa`) with a 5 GB quota, using Error-level logging only to minimize storage usage.
- **NSG rules** were manually reviewed and updated to restrict inbound access to a specific public IP, eliminating exposure to the internet.
- **RDP access via public IP failed**, but connectivity through the VNet was successful. This was likely due to either:
  - NSG rules blocking public traffic
  - VM missing a public IP assignment
  - OS-level firewall settings
- **Defender for Servers**, **Defender CSPM**, and **Defender for Storage** were intentionally left disabled to avoid triggering paid services.
- **Secure Score** was observed at 0% due to pending evaluations. No critical or high-risk recommendations were present at the time of initial scan.
- **Compliance benchmark** (MCSB) was active and showed 57 out of 61 controls passed, indicating strong baseline posture.

---

## 📌 Free-Tier Strategy

All remediation steps were performed using services and configurations eligible under Azure’s 12-month free-tier plan. This lab demonstrates how to achieve meaningful security posture improvements without incurring additional costs.
