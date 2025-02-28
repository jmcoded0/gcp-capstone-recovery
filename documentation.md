# **Google Cloud Security Remediation Case Study**

## **Overview of Security Command Center Dashboard**
This screenshot shows the initial overview of the **Security Command Center** dashboard immediately after logging into the **Google Cloud Console**. It provides a general view of the dashboard layout and available sections.

![Security Command Center Dashboard Overview](https://github.com/user-attachments/assets/f822669a-0a4b-4ac6-b6f4-a0974cdac323)

## **Active Vulnerabilities Overview**
This screenshot displays the **active vulnerabilities** identified by the **Security Command Center**. It shows a categorized list of findings by resource type, highlighting the **severity** of each vulnerability.

<img width="960" alt="Active Vulnerabilities in Security Command Center" src="https://github.com/user-attachments/assets/77125f3d-fcb7-41af-887c-e3e4e2d3f7c6" />

The next step was to examine the **PCI DSS 3.2.1 compliance report** to identify non-compliant rules and understand specific vulnerabilities that needed remediation.

---

## **PCI DSS 3.2.1 Compliance Report Analysis**
After analyzing the **Security Command Center** dashboard and active vulnerabilities, the next step was to review the **PCI DSS 3.2.1 compliance report**. This report provided insights into the specific **vulnerabilities** and **non-compliant rules** contributing to the data breach.

<img width="960" alt="PCI DSS 3.2.1 Compliance Report" src="https://github.com/user-attachments/assets/809c25ca-eb97-467a-9a4d-885396dc041c" />

### **Key Security Issues Identified:**
✅ **High Severity Findings:**
- **Publicly accessible Cloud Storage buckets**
- **VMs with public IP addresses**
- **Overly permissive firewall rules**

❌ **Non-Compliance Issues:**
- Open **RDP and SSH ports**
- **Public bucket ACLs**
- **VMs exposed to the internet**

These findings indicated a **critical lack of security controls** and **non-compliance** with essential **PCI DSS requirements**.

---

## **Security Command Center Findings Analysis**

### **Cloud Storage Bucket Findings**
The **Security Command Center** flagged several issues related to **Cloud Storage**, including:

- **Public bucket ACL** → The bucket was publicly accessible.
- **Bucket policy only disabled** → No explicit **bucket policy** was in place.

<img width="959" alt="ss7" src="https://github.com/user-attachments/assets/8a4c63a2-2dd6-47fa-be0c-b77149a1a2fe" />

🔒 **Remediation:**
- **Revoked public access** to the storage bucket.
- **Enabled Uniform bucket-level access** to enforce tighter security policies.
- **Removed all user permissions** from the bucket.

### **Compute Engine Instance Findings**
The **cc-app-01 Compute Engine instance** had multiple security risks:

- **Malware bad domain** → The instance accessed a domain associated with malware.
- **Compute secure boot disabled** → Secure boot was not enabled.
- **Default service account used** → Used default service account with excessive permissions.
- **Public IP address** → The instance had a **public IP**.
- **Full API access** → Allowed unrestricted Cloud API access.

<img width="960" alt="ss8" src="https://github.com/user-attachments/assets/6d22e383-37ea-42a7-91ab-d1e871f4aa60" />

🔒 **Remediation:**
- **Deleted compromised VM** and created a **new VM** from a pre-infection snapshot.
- **Enabled secure boot** for protection against unauthorized firmware changes.
- **Restricted API permissions** by removing the default service account.
- **Removed the public IP** and configured **private networking**.

---

## **Firewall Configuration and Remediation**

<img width="960" alt="ss18" src="https://github.com/user-attachments/assets/412d6205-c45c-4004-8bc4-867bc75628ab" />

🔒 **Remediation Actions:**
- **Deleted default-allow-icmp, default-allow-rdp, and default-allow-ssh** firewall rules.
- **Created a new firewall rule** (**limit-ports**) to restrict SSH access **only** to **Google Cloud Identity-Aware Proxy (IAP)** IP ranges.
- **Enabled logging** to track network traffic.

---

## **Testing and Validation**
After remediation, a **new PCI DSS 3.2.1 compliance report** was generated to verify security fixes.

<img width="960" alt="ss19" src="https://github.com/user-attachments/assets/9f2c0195-0b82-4f7a-9507-cde0bf9aceab" />

✅ **Verification Steps:**
- Successfully **created and configured a secure VM**.
- Confirmed **Cloud Storage bucket restrictions**.
- Verified **firewall restrictions and logging enablement**.
- Ensured the **PCI DSS 3.2.1 report** reflected successful remediation.

📈 **Security Score:** **Before: 60% compliance → After: 95% compliance**

---

## **Security Considerations**
The following security principles were implemented:

✅ **Least Privilege Access** → Limited permissions across cloud resources.
✅ **Network Security** → Restricted open ports and enforced firewall rules.
✅ **Data Protection** → Revoked public storage access and enforced IAM controls.
✅ **Logging & Monitoring** → Enabled logging for visibility into network activity.
✅ **Secure Boot & System Hardening** → Ensured instances boot securely.

---

## **Lessons Learned**
🔍 **Key Takeaways from the Project:**
- **Regular security audits** are essential to prevent vulnerabilities.
- **Least privilege** minimizes the risk of data breaches.
- **Firewall rules should be restrictive by default.**
- **Snapshots** are a valuable tool for recovering compromised systems.
- **Enabling logging & monitoring** helps detect unauthorized access.
- **Secure boot** should be enforced for all Compute Engine instances.

---

## **Future Security Improvements**
🔹 **Implement automated security monitoring & alerting.**
🔹 **Conduct regular penetration testing.**
🔹 **Develop incident response playbooks.**
🔹 **Automate snapshots for quick recovery.**
🔹 **Refine IAM permissions with granular access controls.**
🔹 **Deploy Intrusion Detection & Prevention Systems (IDPS).**
🔹 **Regularly update & patch cloud workloads.**
🔹 **Enforce multi-factor authentication (MFA).**
🔹 **Strengthen data loss prevention (DLP) measures.**
🔹 **Conduct continuous security awareness training.**

---

## **Conclusion**
This project successfully simulated a **data breach** and demonstrated effective **remediation** strategies within a **Google Cloud** environment. By addressing vulnerabilities, restricting access, and validating security fixes, the project improved compliance with **PCI DSS 3.2.1** and enhanced the overall **security posture**.

🚀 **Final Thought:** Cloud security is an ongoing process—**continuous monitoring, proactive remediation, and strong security policies** are key to protecting sensitive data from evolving threats.

