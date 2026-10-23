# Botium Toys: Internal Security Audit

> **Project type:** Security audit and compliance assessment  
> **Course:** Google Cybersecurity Certificate, *Manage Security Risks*  
> **Scenario:** Fictional organisation, Botium Toys  
> **Status:** Learning project based on course-provided materials

## Overview

This project documents an internal security audit of Botium Toys, a fictional toy retailer with a physical store, office, warehouse, and growing online customer base. The audit reviews the company's existing security controls, identifies gaps against selected compliance best practices, and prioritises recommendations to improve its security posture.

The assessment is based on the course-provided **Scope, Goals, and Risk Assessment Report**, **Control Categories** guide, and **Controls and Compliance Checklist**, cross-checked against the course exemplar.

## Objectives and scope

The audit covers the security programme and IT-managed assets described in the scenario, including:

- On-premises equipment and employee devices
- Retail products, warehouse inventory, and online storefront systems
- Accounting, telecommunications, database, security, e-commerce, and inventory systems
- Internet access and the internal network
- Data retention and storage
- Legacy systems requiring manual monitoring

The goal is to identify missing or inadequate controls, consider compliance gaps relating to payment card data and EU customer data, and recommend actions that reduce risk to critical assets and business continuity.

## Risk assessment summary

The course report assigns Botium Toys a **risk score of 8/10**, described as fairly high. The main issues are inadequate asset management, missing controls, and incomplete adherence to compliance best practices.

Key observations from the supplied report:

- All employees can access internally stored data and may be able to access payment card data and customers' personal information.
- Credit card information is not encrypted.
- Least privilege and separation of duties have not been implemented.
- There is no intrusion detection system, no disaster recovery plan, and no backup of critical data.
- Password requirements are weak, and there is no centralised password management system.
- Legacy systems are monitored and maintained, but there is no regular schedule and intervention procedures are unclear.
- A firewall, monitored antivirus, physical locks, CCTV, and functioning fire detection/prevention systems are in place.
- A plan exists to notify EU customers within 72 hours of a data breach, and privacy policies and procedures are documented and enforced.
- The IT department reports that data integrity and availability controls are in place, although broad access means availability is not limited to people who need the data.

## 1. Controls assessment

Answers reflect the course exemplar and the supplied risk report. “No” means the control is missing or not adequately implemented as described in the scenario.

| Control | In place? | Evidence / explanation |
|---|:---:|---|
| Least privilege | No | All employees have access to internally stored data; access should be limited according to job responsibilities. |
| Disaster recovery plans | No | The report states that no disaster recovery plans are in place. |
| Password policies | No | A policy exists, but requirements are minimal and not aligned with current password security expectations. |
| Separation of duties | No | Separation of duties has not been implemented. The exemplar also notes that the CEO manages day-to-day operations and payroll. |
| Firewall | Yes | A firewall blocks traffic according to defined security rules. |
| Intrusion detection system (IDS) | No | The IT department has not installed an IDS. |
| Backups | No | Critical data is not backed up. |
| Antivirus software | Yes | Antivirus is installed and regularly monitored by IT. |
| Manual monitoring, maintenance, and intervention for legacy systems | No | Legacy systems receive some monitoring and maintenance, but there is no regular schedule and intervention procedures are unclear. |
| Encryption | No | Credit card information is not encrypted. |
| Password management system | No | There is no centralised password management system. |
| Locks (offices, storefront, warehouse) | Yes | The report describes sufficient locks at the physical location. |
| CCTV surveillance | Yes | CCTV is described as up to date and functioning. |
| Fire detection/prevention | Yes | Fire detection and prevention systems are functioning. |

## 2. PCI DSS compliance review

| Best practice | Compliant? | Evidence / explanation |
|---|:---:|---|
| Only authorised users can access customers' credit card information | No | All employees can access internal data, potentially including cardholder information. |
| Credit card information is stored, accepted, processed, and transmitted in a secure environment | No | Broad access and lack of encryption expose payment card information to risk. |
| Implement data encryption procedures | No | The report states that credit card information is not encrypted. |
| Adopt secure password management policies | No | Password requirements are weak and no centralised password management system is in place. |

## 3. GDPR compliance review

| Best practice | Compliant? | Evidence / explanation |
|---|:---:|---|
| EU customers' data is kept private and secure | No | Broad internal access and the lack of encryption for financial information undermine confidentiality. |
| Notify EU customers within 72 hours of a breach | Yes | The report confirms a plan to notify EU customers within 72 hours. |
| Ensure data is properly classified and inventoried | No | Assets have been listed, but they have not been properly classified; the report identifies asset management as inadequate. |
| Enforce privacy policies, procedures, and processes to document and maintain data | Yes | Privacy policies, procedures, and processes have been developed and are enforced. |

## 4. SOC 1 / SOC 2 best-practice review

| Best practice | In place? | Evidence / explanation |
|---|:---:|---|
| User access policies are established | No | Least privilege and separation of duties are not in place, and all employees have access to internal data. |
| Sensitive data (PII/SPII) is confidential and private | No | Encryption is not used to help protect sensitive information, and access is too broad. |
| Data integrity ensures data is consistent, complete, accurate, and validated | Yes | The report states that IT has integrated controls to ensure data integrity. |
| Data is available to individuals authorised to access it | No | Data is available broadly to employees; access should be restricted to people who need it for their roles. |

## 5. Recommendations and priority actions

### Priority 1: Restrict access and protect sensitive data

- Implement **least privilege** and role-based access so employees only access the data needed for their jobs.
- Introduce **separation of duties** for sensitive tasks to reduce the risk of error, fraud, or misuse.
- Encrypt sensitive information, particularly payment card data, both at rest and in transit where applicable.
- Review data access permissions and document who is authorised to access personal and payment data.

### Priority 2: Improve resilience and detection

- Create and test a disaster recovery plan.
- Establish regular, protected backups of critical data and test restoration.
- Implement an intrusion detection capability and define how alerts will be investigated and escalated.
- Establish a documented maintenance schedule and clear intervention procedures for legacy systems.

### Priority 3: Strengthen identity and password practices

- Improve password requirements and implement a centralised password manager.
- Review account creation, access changes, and account removal processes.
- Periodically review access rights, especially for privileged accounts.

### Priority 4: Improve asset management and compliance evidence

- Maintain an accurate asset inventory and classify assets and data by sensitivity and business impact.
- Review PCI DSS and GDPR-related requirements relevant to the company's actual processing activities.
- Retain evidence of policies, control operation, testing, and remediation.
- Test the breach response and EU notification process periodically.

The organisation should assign owners and target dates to these actions, starting with access control, encryption, backups, and recovery planning. Progress should be tracked and reviewed by the IT manager.

## Key takeaways: What I learned

- **An audit is evidence-led.** A control should not be marked as implemented just because it is common practice; the decision needs to be supported by the available report or evidence.
- **Security controls work in layers.** Administrative controls (policies and responsibilities), technical controls (firewalls, IDS, encryption), and physical controls (locks and CCTV) support one another as defence in depth.
- **Confidentiality, integrity, and availability are connected but distinct.** Access restrictions and encryption support confidentiality; integrity controls help maintain accurate data; backups and recovery plans support availability and business continuity.
- **Least privilege reduces unnecessary exposure.** Giving every employee access to internal data increases the impact of compromised accounts and insider misuse.
- **Having a policy is not the same as having an effective control.** Botium Toys has a password policy, but weak requirements and the absence of a central password manager leave important gaps.
- **Prevention, detection, and recovery all matter.** A firewall may block unwanted traffic, an IDS can help identify suspicious activity, and tested backups and recovery plans help the business recover after an incident.
- **Compliance depends on practical safeguards and evidence.** Policies, access restrictions, data classification, encryption, and breach-response procedures need to be implemented and maintained, not merely documented.
- **Risk assessment helps prioritise work.** With a reported risk score of 8/10, Botium Toys should address the most consequential gaps first and track remediation to completion.
- **Security is an ongoing process.** Asset inventories, access reviews, legacy system maintenance, control testing, and compliance reviews need to be repeated as the business changes.

## Limitations

This is a learning exercise based on a fictional company and the documents supplied in the Google Cybersecurity Certificate course. It is not a formal compliance certification, penetration test, or legal opinion. The checklist records the scenario's stated facts and does not independently verify controls.

## Learning source

Google Cybersecurity Certificate — *Manage Security Risks*, Botium Toys internal security audit activity. The assessment was completed using the course's scope and risk assessment report, control categories guide, and completed checklist exemplar.
