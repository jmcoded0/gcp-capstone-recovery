## Overview of Security Command Center Dashboard

This screenshot shows the initial overview of the Security Command Center dashboard immediately after logging into the Google Cloud Console. It provides a general view of the dashboard's layout and available sections.

![Security Command Center Dashboard Overview](https://github.com/user-attachments/assets/f822669a-0a4b-4ac6-b6f4-a0974cdac323)

## Active Vulnerabilities Overview

This screenshot displays the active vulnerabilities identified by the Security Command Center. It shows a list of findings categorized by resource type, highlighting the severity of each vulnerability.

<img width="960" alt="Active Vulnerabilities in Security Command Center" src="https://github.com/user-attachments/assets/77125f3d-fcb7-41af-887c-e3e4e2d3f7c6" />

The next step was to examine the PCI DSS 3.2.1 compliance report to identify non-compliant rules and understand the specific vulnerabilities that needed to be addressed.

## PCI DSS 3.2.1 Compliance Report Analysis

After examining the Security Command Center dashboard and the active vulnerabilities, the next step was to analyze the PCI DSS 3.2.1 compliance report. This report provided insights into the specific vulnerabilities and non-compliant rules that contributed to the data breach.

<img width="960" alt="PCI DSS 3.2.1 Compliance Report" src="https://github.com/user-attachments/assets/809c25ca-eb97-467a-9a4d-885396dc041c" />

The report highlighted several high-severity findings, including publicly accessible Cloud Storage buckets, VMs with public IP addresses, and overly permissive firewall rules. These findings indicated a critical lack of security controls and non-compliance with essential PCI DSS requirements. Specifically, the report showed non-compliance in areas such as open RDP and SSH ports, public bucket ACLs, and VMs with public IP addresses.

## Security Command Center Findings Analysis

### Cloud Storage Bucket Findings

The Security Command Center identified several findings related to the Cloud Storage bucket, including:

* Public bucket ACL: This finding indicated that the bucket was publicly accessible.
* Bucket policy only disabled: This indicated that there was no explicit bucket policy in place.

<img width="959" alt="ss7" src="https://github.com/user-attachments/assets/8a4c63a2-2dd6-47fa-be0c-b77149a1a2fe" />

These findings highlighted the risk of unauthorized access to sensitive data stored in the bucket.

### Compute Engine Instance Findings

The findings related to the Compute Engine instance, cc-app-01, included:

* Malware bad domain: This indicated that the instance had accessed a domain associated with malware.
* Compute secure boot disabled: This showed that secure boot was not enabled.
* Default service account used: This indicated the use of the default service account with excessive permissions.
* Public IP address: This showed that the instance had a public IP address.
* Full API access: This indicated that the instance had full access to all Cloud APIs.

<img width="960" alt="ss8" src="https://github.com/user-attachments/assets/6d22e383-37ea-42a7-91ab-d1e871f4aa60" />

These findings suggested that the instance was compromised and highly vulnerable.

### Firewall Configuration and Remediation

While a direct screenshot of the Security Command Center's "Firewall Findings" is unavailable, the following screenshots demonstrate the steps taken to address the firewall vulnerabilities:

<img width="960" alt="ss17" src="https://github.com/user-attachments/assets/01861c3d-641a-4217-8a8a-2602cf7c2fb3" />


The firewall configuration was modified to restrict access to critical ports and enable logging. Specific actions included:

* Creating a new firewall rule to restrict SSH access to authorized IP addresses.
* Deleting overly permissive firewall rules that allowed open access to RDP and SSH ports.
* Enabling logging for remaining firewall rules to track network traffic.

These actions were taken to mitigate the risk of unauthorized access and improve network visibility.
