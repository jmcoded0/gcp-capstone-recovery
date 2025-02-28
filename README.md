# gcp-capstone-recovery

## Respond and Recover from a Data Breach Experiment  

### Introduction  

This project documents the process of responding to and recovering from a simulated data breach within a Google Cloud Platform (GCP) environment. The objective was to identify and remediate vulnerabilities, isolate and contain the breach, recover compromised systems, and ensure compliance with security frameworks.  

### Google Cloud Services Used  

- Google Cloud Security Command Center (SCC)  
- Compute Engine  
- Cloud Storage  
- Identity and Access Management (IAM)  
- Virtual Private Cloud (VPC) Firewall Rules  

### Project Architecture  

The project simulated a real-world scenario where a retail company, **Cymbal Retail**, experienced a data breach. The architecture involved:  

- A **compromised Compute Engine virtual machine (VM)** that was used to access sensitive data.  
- A **publicly accessible Cloud Storage bucket** containing sensitive information.  
- **VPC firewall rules** that allowed overly permissive access to the network.  
- **Security Command Center** to identify and view vulnerabilities.  

### Key Steps in Incident Response  

#### **1. Identifying and Analyzing the Breach**  
- Used **Google Cloud Security Command Center (SCC)** to detect security findings.  
- Examined the **PCI DSS 3.2.1 compliance report** for non-compliant rules.  

#### **2. Containment and Eradication**  
- Shut down the **compromised VM** and created a new VM from a **snapshot** taken before the breach.  
- Revoked **public access** to the **Cloud Storage bucket** and enforced **uniform bucket-level access control**.  
- Removed **excessive permissions** from IAM roles.  

#### **3. Firewall Remediation**  
- Deleted default **allow rules for RDP, ICMP, and SSH**.  
- Created a **new firewall rule** to restrict SSH access to authorized IP ranges.  
- **Enabled logging** for all firewall rules to improve network visibility.  

#### **4. Compliance Verification**  
- Ran a **PCI DSS 3.2.1 compliance report** after remediation.  
- Verified that major vulnerabilities had been resolved.  

### Security Enhancements Implemented  

- **Enforced the least privilege principle** for IAM roles.  
- **Restricted network access** by limiting firewall rules.  
- **Ensured secure boot** was enabled on Compute Engine VMs.  
- **Enabled logging** to track security events.  
- **Implemented snapshots** for disaster recovery.  

### Results & Lessons Learned  

- **Importance of security monitoring**: Continuous monitoring is key to detecting breaches.  
- **Least privilege enforcement**: Overly permissive IAM roles can lead to major security risks.  
- **Firewall restrictions**: Open ports increase the attack surface and should be restricted.  
- **Logging and auditing**: Essential for incident response and forensic analysis.  

### Future Improvements  

- Implement **Intrusion Detection and Prevention Systems (IDPS)**.  
- Automate **security monitoring and compliance checks**.  
- Conduct **regular security audits and penetration testing**.  
- Implement **Data Loss Prevention (DLP) policies**.  
- Enhance **incident response automation** with Security Orchestration, Automation, and Response (SOAR).  

### Project Link  

📌 **[View the full project on GitHub](YOUR_GITHUB_PROJECT_LINK_HERE)**  

---  

This should be good to copy and paste into your GitHub repo. Just replace `YOUR_GITHUB_PROJECT_LINK_HERE` with your actual GitHub project URL. Let me know if you want any modifications! 🚀
