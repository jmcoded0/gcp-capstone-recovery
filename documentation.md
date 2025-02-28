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

<img width="960" alt="ss18" src="https://github.com/user-attachments/assets/412d6205-c45c-4004-8bc4-867bc75628ab" />

This screenshot shows the creation of the "limit-ports" firewall rule. This rule restricts SSH access to instances tagged with "cc" from the IP range 35.235.240.0/20, which is used by Google Cloud's Identity-Aware Proxy (IAP). This rule was created to replace the overly permissive default SSH rule.

The firewall configuration was modified to restrict access to critical ports and enable logging. Specific actions included:

* Creating a new firewall rule to restrict SSH access to authorized IP addresses.
* Deleting overly permissive firewall rules that allowed open access to RDP and SSH ports.
* Enabling logging for remaining firewall rules to track network traffic.

These actions were taken to mitigate the risk of unauthorized access and improve network visibility.

## Project Architecture

The project simulated a real-world scenario where a retail company, Cymbal Retail, experienced a data breach. The architecture involved:

* A compromised Compute Engine virtual machine (VM) that was used to access sensitive data.
* A publicly accessible Cloud Storage bucket containing sensitive information.
* VPC firewall rules that allowed overly permissive access to the network.
* Security Command Center to identify and view vulnerabilities.

## Testing and Validation

The following tests were performed to validate the remediation efforts:

<img width="960" alt="ss19" src="https://github.com/user-attachments/assets/9f2c0195-0b82-4f7a-9507-cde0bf9aceab" />

This screenshot shows the updated PCI DSS 3.2.1 compliance report after the remediation steps were completed. It confirms that the high-severity findings related to open RDP and SSH ports, public bucket ACLs, and VMs with public IP addresses have been successfully addressed.

* Verified the successful creation and configuration of the new VM.
* Confirmed the removal of public access and restricted permissions on the Cloud Storage bucket.
* Tested SSH access to the new VM from authorized IP addresses.
* Verified the deletion of overly permissive firewall rules and the enabling of logging.
* Confirmed that the PCI DSS 3.2.1 report showed that the vulnerabilities were remediated.

## Security Considerations

The following security considerations were implemented:

* Implemented least privilege principle by creating a new VM without a default service account.
* Restricted network access by limiting firewall ports.
* Ensured data security by revoking public access to the Cloud Storage bucket.
* Used snapshots to recover compromised systems.
* Enabled logging on firewall rules to track network traffic.
* Ensured secure boot was enabled.

## Conclusion

This project successfully simulated a data breach scenario and demonstrated the ability to respond to and recover from such incidents within a Google Cloud environment. By identifying and remediating vulnerabilities, isolating and containing the breach, and recovering compromised systems, the project achieved its objectives. The successful verification of compliance with the PCI DSS 3.2.1 standard further validated the effectiveness of the implemented security measures.

## Lessons Learned

* The importance of regular security audits and vulnerability assessments.
* The significance of implementing the principle of least privilege.
* The need for robust network security configurations.
* The effectiveness of using snapshots for system recovery.
* The importance of logging.
* The need to ensure secure boot is enabled.

## Future Improvements

* Implement automated security monitoring and alerting.
* Conduct regular penetration testing to identify potential vulnerabilities.
* Develop and implement incident response plans.
* Automate snapshots.
* Implement more granular IAM permissions.
* Implement Intrusion Detection and Prevention Systems (IDPS).
* Regularly update and patch systems and applications.
* Implement multi-factor authentication (MFA) for all users.
* Implement data loss prevention (DLP) measures.
* Conduct regular security awareness training for employees.
