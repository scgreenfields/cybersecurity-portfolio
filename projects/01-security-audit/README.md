# Project 1: Internal Security Audit & Risk Assessment (Botium Toys)

## Objective
To evaluate the overall security posture of Botium Toys, assess existing IT assets against the NIST Cybersecurity Framework (CSF), and identify compliance gaps regarding PCI DSS, GDPR, and SOC controls.

## Tools & Frameworks Used
* **Framework:** NIST Cybersecurity Framework (CSF)
* **Standards & Regulations:** PCI DSS, GDPR, SOC 1 / SOC 2
* **Tools:** Controls and Compliance Assessment Checklist, Risk Assessment Matrix

## Scenario & Scope
Botium Toys is a growing U.S. toy retailer expanding its online presence globally. The audit scope covers the company's security program, including on-premises equipment, physical storefront/warehouse assets, internal networks, data retention systems, and legacy software.

---

## 📋 Controls Assessment Summary

### Administrative / Managerial Controls
| Control | Implemented? | Notes / Context |
| :--- | :---: | :--- |
| **Least Privilege** | **No** | Employees currently have access to all internal data, including payment info and customer PII/SPII. |
| **Separation of Duties** | **No** | Access controls defining separation of duties have not been implemented. |
| **Password Policies** | **No** | Requirements are nominal and fail to meet minimum complexity standards. |
| **Disaster Recovery Plan (DRP)** | **No** | No formal DRP exists to restore operations after a major incident. |

### Technical Controls
| Control | Implemented? | Notes / Context |
| :--- | :---: | :--- |
| **Firewall** | **Yes** | Active firewall deployed with defined security rules to filter network traffic. |
| **Antivirus (AV) Software** | **Yes** | Installed and monitored regularly on endpoints by IT staff. |
| **Data Encryption** | **No** | Encryption is absent for customer credit card info at rest and in transit. |
| **Intrusion Detection System (IDS)** | **No** | No IDS is installed to detect anomalous network traffic. |
| **Data Backups** | **No** | The company does not maintain backups of critical business data. |
| **Centralized Password Management** | **No** | Lacks a centralized system to enforce rules and reduce password fatigue. |

### Physical / Operational Controls
| Control | Implemented? | Notes / Context |
| :--- | :---: | :--- |
| **Locks** | **Yes** | Facilities (offices, storefront, warehouse) have sufficient physical locks. |
| **CCTV Surveillance** | **Yes** | Functional, up-to-date CCTV cameras installed across facilities. |
| **Fire Detection & Prevention** | **Yes** | Functioning fire alarms and sprinkler systems are operational. |

---

## ⚖️ Compliance Assessment Summary

* **PCI DSS (Payment Card Industry):** **Non-Compliant.** Cardholder data is stored locally in plaintext without encryption, and access is not restricted under least privilege.
* **GDPR (EU Data Protection):** **Non-Compliant.** Customer PII/SPII is exposed enterprise-wide without encryption or proper data inventory controls (though a 72-hour breach notification plan exists).
* **SOC 1 / SOC 2:** **Non-Compliant.** Lacks user access policies, least privilege enforcement, data backups, and disaster recovery planning.

---

## 💡 Key Recommendations

1. **Implement End-to-End Encryption (PCI DSS & GDPR):** Deploy AES-256 encryption across all transaction touchpoints and local databases holding cardholder info or EU customer PII/SPII.
2. **Enforce Role-Based Access Control (Least Privilege):** Restrict access to sensitive customer data strictly to authorized personnel whose job functions require it.
3. **Establish Off-Site Backups & Disaster Recovery:** Create automated, regular backups of critical data and document a formal DRP to maintain business continuity.
4. **Deploy IDS & Centralized Password Management:** Install an Intrusion Detection System alongside the firewall and adopt a centralized password manager to enforce password complexity rules.
