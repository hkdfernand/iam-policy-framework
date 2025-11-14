# IAM Policy Framework

**Author:** Fernand Havugimana  
**Purpose:** Comprehensive Identity and Access Management policy documentation template

## Overview

This IAM Policy Framework provides a comprehensive template for organizations implementing or enhancing their Identity and Access Management programs. It covers access control procedures, user lifecycle management, privileged access guidelines, and compliance requirements aligned with industry standards including NIST, ISO 27001, and SOX.

## Policy Components

### 1. Access Control Policy

#### 1.1 Purpose
To establish standards for granting, reviewing, and revoking user access to organizational information systems and data.

#### 1.2 Scope
This policy applies to all employees, contractors, vendors, and third parties requiring access to company systems and data.

#### 1.3 Policy Statements

**Principle of Least Privilege:**
- Users shall be granted the minimum level of access necessary to perform their job functions
- Access beyond role requirements requires documented business justification and management approval

**Role-Based Access Control (RBAC):**
- Access permissions shall be assigned based on predefined roles aligned with job functions
- Each role shall have documented access requirements and approval workflows
- Role definitions shall be reviewed annually and updated as needed

**Segregation of Duties (SoD):**
- No single individual shall have conflicting permissions that could enable fraud or error
- Systems shall enforce SoD policies and flag violations for remediation
- Documented exceptions require executive approval and compensating controls

**Authentication Requirements:**
- All users must authenticate using unique credentials
- Shared accounts are prohibited except for documented service accounts
- Multi-Factor Authentication (MFA) is required for:
  - All remote access
  - Privileged/administrative accounts
  - Access to sensitive data (PII, financial, customer data)
  - Cloud-based applications

---

### 2. User Lifecycle Management

#### 2.1 Provisioning (Joiner Process)

**Pre-Arrival:**
- HR submits access request 5 business days before start date
- Hiring manager specifies role and department
- IT creates accounts based on role template

**Day 1:**
- User receives credentials securely (not via email)
- Required: password change on first login
- User completes security awareness training within 7 days

**Access Approval:**
- Standard access: Automated based on role
- Non-standard access: Manager approval required
- Sensitive data access: Security team approval required

#### 2.2 Account Modifications (Mover Process)

**Job Changes:**
- HR notifies IT of role changes within 24 hours
- Previous access reviewed and modified within 3 business days
- New role access provisioned based on role template
- Manager certification required for transfers

**Temporary Access:**
- Maximum duration: 90 days
- Requires business justification and manager approval
- Automated expiration enforced
- Extension requires re-approval

#### 2.3 De-Provisioning (Leaver Process)

**Termination Process:**
- HR notifies IT immediately upon termination decision
- Voluntary separation: Accounts disabled on last working day
- Involuntary separation: Accounts disabled immediately
- All access revoked within 24 hours of separation

**Access Removal Checklist:**
- [ ] Active Directory account disabled
- [ ] Email access revoked
- [ ] VPN access terminated
- [ ] Application accounts disabled
- [ ] Physical access cards deactivated
- [ ] Mobile device access removed
- [ ] Shared mailbox access transferred
- [ ] Manager confirmation of completion

---

### 3. Access Review & Certification

#### 3.1 Frequency
- **User Access:** Quarterly certification by managers
- **Privileged Access:** Monthly review by security team
- **Service Accounts:** Semi-annual review by application owners
- **Contractor/Vendor Access:** Monthly review

#### 3.2 Certification Process

**Manager Responsibilities:**
- Review all team members' access quarterly
- Certify appropriate access or request removal
- Document business justification for exceptions
- Complete certification within 15 days of notification

**Certification Campaign Workflow:**
1. System generates access reports by manager
2. Automated email notifications sent to certifiers
3. Managers review and approve/revoke access
4. Reminders sent at day 7, 10, and 13
5. Escalation to senior management for non-completion
6. IT implements access changes within 5 business days
7. Audit report generated showing completion status

**Non-Compliance:**
- Uncertified accounts flagged for review
- Accounts without manager certification for 30+ days: Disabled
- Managers missing certifications: Reported to leadership

---

### 4. Privileged Access Management (PAM)

#### 4.1 Definition of Privileged Accounts
- Domain administrators
- Database administrators
- System administrators
- Security administrators
- Application administrators
- Accounts with sudo/root access
- Service accounts with elevated privileges

#### 4.2 Privileged Access Requirements

**Access Controls:**
- Privileged accounts separate from standard accounts
- No shared privileged credentials
- Just-in-time (JIT) access where feasible
- All privileged sessions logged and monitored
- Automated alerts for suspicious privileged activity

**Authentication:**
- MFA required for all privileged access
- Password complexity: Minimum 16 characters
- Password rotation: Every 60 days (or passwordless authentication)
- Session timeout: 15 minutes of inactivity

**Monitoring:**
- Real-time SIEM alerts for privileged actions
- Weekly review of privileged access logs
- Quarterly audit of privileged account usage
- Annual penetration testing of privileged access controls

#### 4.3 Emergency Access Procedures
- "Break glass" accounts for emergency situations
- Stored in secure password vault
- All usage reviewed within 24 hours
- Justification required for each use

---

### 5. Password Policy

#### 5.1 Password Requirements

**Complexity:**
- Minimum length: 12 characters (16 for privileged accounts)
- Must contain: uppercase, lowercase, number, special character
- Cannot contain: username, common words, previous passwords

**Expiration:**
- Standard accounts: 90 days
- Privileged accounts: 60 days
- Service accounts: 180 days with automated rotation

**Failed Login Attempts:**
- Account locked after 5 failed attempts
- 30-minute lockout duration
- Administrator notification after 3 lockouts in 24 hours

#### 5.2 Password Management

**Prohibited Practices:**
- Writing passwords down
- Sharing passwords
- Storing passwords in unencrypted files
- Reusing passwords across systems
- Using same password for personal and work accounts

**Approved Practices:**
- Use of company-approved password manager
- Passwordless authentication (biometrics, FIDO2 keys)
- Single Sign-On (SSO) where available

---

### 6. Remote Access Policy

#### 6.1 Requirements
- VPN required for all remote connections
- MFA required for VPN authentication
- Company-managed devices only (no BYOD for production access)
- Endpoint security software required (antivirus, EDR)

#### 6.2 Restrictions
- No remote access from public computers
- No storage of company data on personal devices
- VPN auto-disconnect after 12 hours
- Geo-blocking for high-risk countries

---

### 7. Third-Party Access

#### 7.3 Vendor Access Requirements
- Separate vendor accounts (no employee account sharing)
- Time-limited access (maximum 1 year)
- Quarterly access reviews
- NDA and security agreements required
- Access restricted to specific systems/data needed
- All vendor actions logged and monitored

#### 7.2 Vendor Account Lifecycle
1. Vendor contract established with security requirements
2. Business owner submits vendor access request
3. Security team reviews and approves
4. Separate vendor account created
5. Access granted for contract duration only
6. Quarterly certification by business owner
7. Automatic de-provisioning at contract end

---

### 8. Compliance & Audit

#### 8.1 Regulatory Requirements
This policy supports compliance with:
- **SOX (Sarbanes-Oxley):** Segregation of duties, access reviews
- **PCI-DSS:** Unique IDs, access restrictions, audit logging
- **HIPAA:** Access controls, audit trails, workforce clearance
- **GDPR:** Data access controls, user rights, breach notification
- **NIST 800-53:** Access control family (AC) requirements
- **ISO 27001:** A.9 (Access Control) requirements

#### 8.2 Audit Requirements

**Documentation:**
- All access requests and approvals retained for 7 years
- Access review certifications retained for 7 years
- Audit logs retained for 1 year (online), 7 years (archive)
- Policy exceptions documented with compensating controls

**Audit Activities:**
- Quarterly internal access control audits
- Annual external audit (SOX, regulatory)
- Monthly automated compliance scans
- Ad-hoc audits for security incidents

**Metrics & Reporting:**
- Monthly: Privileged account review completion rate
- Quarterly: Access certification completion rate, SoD violations
- Annual: Policy exceptions, access-related incidents, audit findings

---

### 9. Incident Response

#### 9.1 Access-Related Incidents

**Types of Incidents:**
- Unauthorized access attempts
- Compromised credentials
- Privilege escalation
- Insider threats
- Shared account usage
- Policy violations

#### 9.2 Response Procedures

**Immediate Actions (Within 1 hour):**
1. Disable compromised account(s)
2. Notify security team and user's manager
3. Preserve audit logs
4. Assess scope of unauthorized access

**Investigation (Within 24 hours):**
1. Review access logs for suspicious activity
2. Identify data/systems accessed
3. Interview user (if appropriate)
4. Document timeline and impact

**Remediation:**
1. Reset credentials for affected accounts
2. Review and revoke unnecessary access
3. Implement additional monitoring
4. Report to leadership and compliance team
5. Update security controls as needed

---

### 10. Roles & Responsibilities

#### 10.1 Executive Management
- Approve IAM policies and funding
- Receive quarterly access governance reports
- Approve policy exceptions

#### 10.2 Security Team
- Enforce IAM policies
- Monitor access compliance
- Investigate access violations
- Manage privileged access program
- Conduct access audits

#### 10.3 IT Team
- Provision/de-provision user accounts
- Implement technical access controls
- Manage identity systems (AD, IAM platforms)
- Support access certification campaigns

#### 10.4 Managers
- Request access for team members
- Certify team access quarterly
- Remove access promptly when no longer needed
- Report suspected access violations

#### 10.5 Users
- Protect credentials
- Use access appropriately
- Report suspicious activity
- Complete security training
- Comply with access policies

---

### 11. Policy Governance

#### 11.1 Policy Review
- Annual policy review and update
- Updates triggered by: regulatory changes, security incidents, technology changes
- All updates require CISO approval

#### 11.2 Training & Awareness
- Security awareness training: Annually for all users
- IAM-specific training: For IT and security teams
- Manager training: Access certification procedures
- New hire training: Within 7 days of start

#### 11.3 Policy Enforcement
- Policy violations reported to management
- Disciplinary action per HR policy
- Serious violations: Termination and potential legal action

---

## Implementation Checklist

### Phase 1: Foundation (Month 1-2)
- [ ] Document current state of access management
- [ ] Identify gaps against policy requirements
- [ ] Select and implement IAM platform (if needed)
- [ ] Define roles and baseline access

### Phase 2: Process Development (Month 3-4)
- [ ] Create provisioning workflows
- [ ] Document de-provisioning procedures
- [ ] Establish access review process
- [ ] Implement privileged access management

### Phase 3: Automation (Month 5-6)
- [ ] Automate joiner/mover/leaver processes
- [ ] Implement access certification platform
- [ ] Configure SIEM alerts for access violations
- [ ] Enable MFA across all systems

### Phase 4: Continuous Improvement (Ongoing)
- [ ] Quarterly access reviews
- [ ] Monthly metrics reporting
- [ ] Annual policy updates
- [ ] Regular security training

---

## Appendices

### Appendix A: Access Request Form Template
*(To be completed by requesting manager)*
- User Name:
- Employee ID:
- Department:
- Job Title:
- Start Date:
- Access Required (select all that apply):
  - [ ] Email & Office 365
  - [ ] VPN Access
  - [ ] Application Access: ___________
  - [ ] Shared Drive Access: ___________
  - [ ] Other: ___________
- Business Justification:
- Duration (if temporary):
- Manager Approval: __________ Date: __________

### Appendix B: Termination Checklist
*(To be completed by IT on termination date)*
- [ ] AD account disabled
- [ ] Email access revoked
- [ ] VPN disabled
- [ ] Application access removed
- [ ] Shared folder access removed
- [ ] Physical access card deactivated
- [ ] Mobile device wiped
- [ ] Equipment collected
- [ ] Manager notified of completion
- Completed by: __________ Date: __________

### Appendix C: Glossary
- **IAM:** Identity and Access Management
- **RBAC:** Role-Based Access Control
- **SoD:** Segregation of Duties
- **PAM:** Privileged Access Management
- **MFA:** Multi-Factor Authentication
- **JML:** Joiner/Mover/Leaver
- **SSO:** Single Sign-On
- **SIEM:** Security Information and Event Management

---

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Nov 2024 | Fernand Havugimana | Initial policy framework creation |

---

## Contact & Support

**Policy Owner:** Information Security Team  
**Policy Approver:** Chief Information Security Officer (CISO)  
**Review Frequency:** Annual  
**Next Review Date:** November 2025

For questions about this policy, contact:
- **Email:** hkdfernand@gmail.com
- **Author:** Fernand Havugimana - IAM & Cybersecurity Professional

---

*This policy framework template is designed to be customized for your organization's specific needs, regulatory requirements, and technical environment.*
