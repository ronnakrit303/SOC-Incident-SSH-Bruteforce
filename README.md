# SOC Incident Report – SSH Brute Force Attack

**Incident ID:** SOC-2025-001  
**Category:** Credential-Based Intrusion Attempt  
**Status:** Resolved  
**Severity:** High  

This project demonstrates my end-to-end Security Operations Center (SOC) analysis workflow by investigating a simulated SSH brute-force attack that resulted in successful unauthorized system access. The project includes real authentication log analysis, incident classification, MITRE ATT&CK mapping, incident response actions, and formal SOC-style reporting.

The goal of this project is to practice real-world Blue-Team defensive operations and structured cyber incident documentation.

---

## Objectives

- Analyze Linux SSH authentication logs to detect malicious behavior
- Develop SOC-style investigation and documentation skills
- Classify incidents based on impact and evidence
- Apply MITRE ATT&CK mapping to adversary techniques
- Practice Incident Response reporting & remediation planning
- Strengthen a defensive / Blue-Team security mindset

---

## Environment & Tools

- Ubuntu Linux Server (Lab VM)
- OpenSSH service
- System authentication logs (`/var/log/auth.log`)
- Command-line log review tools
- MITRE ATT&CK Framework
- SOC / Incident Response reporting standards

---

## Incident Overview

A series of repeated SSH authentication failures were detected targeting the Linux user account `ubuntu`.  
All failed attempts originated from the same external IP address. Shortly afterward, a successful login occurred using the same credentials — confirming credential compromise and unauthorized account access.

This incident was classified as:

> **True Positive — High Severity Security Incident**

because system authentication was successfully bypassed using brute-forced credentials, granting the attacker valid account access.

---

## Analysis Summary

### Key Observations
- Large volume of failed SSH login attempts  
- Same user account repeatedly targeted  
- Same source IP address across attempts  
- Authentication eventually succeeded  
- Access granted to the target system  

### Root Cause
> Credential-based SSH brute-force attack leading to account compromise

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|--------|----------|----|
| Credential Access | Brute Force | **T1110** |
| Initial Access | Valid Accounts | **T1078** |

---

## Investigation Workflow

1. Collected authentication logs from `/var/log/auth.log`
2. Identified abnormal authentication activity
3. Observed repeated login failures from the same IP
4. Confirmed successful SSH login attempt
5. Determined credential compromise
6. Classified incident as a **True Positive**
7. Mapped behavior to MITRE ATT&CK
8. Executed incident response & mitigation actions
9. Documented findings in SOC-style report

---

## Response & Mitigation Actions

- Reset compromised credentials  
- Terminated unauthorized SSH sessions  
- Disabled password-based SSH authentication  
- Enforced SSH key-based authentication  
- Restricted SSH access to trusted IP ranges  
- Enabled login monitoring & alerting  
- Reviewed host for persistence and privilege escalation  

These actions significantly reduced the likelihood of similar incidents recurring.

---

## Lessons Learned

- Password-based SSH authentication introduces high credential risk  
- Continuous authentication monitoring is essential  
- Brute-force protection & throttling greatly reduces exposure  
- Layered security controls strengthen system resilience  
- Structured IR processes improve containment time  

---

## Deliverable — Full SOC Incident Report

 **Download the complete report (PDF):**

 _Incident Report — SSH Brute Force Attack_  
  
[Incident-Report_SSH-Bruteforce.pdf](Incident-Report_SSH-Bruteforce.pdf)

The report includes:

- Executive Summary  
- Timeline Analysis  
- Attack Pattern Review  
- True/False Positive Classification  
- MITRE Mapping  
- Impact & Severity Assessment  
- Response Actions  
- Evidence Appendix  


---

## What This Project Demonstrates

- SOC Analyst workflow
- Blue-Team defensive thinking
- Log analysis & interpretation
- Threat detection & classification
- MITRE ATT&CK familiarity
- Incident Response methodology
- Professional security reporting
- Attention to documentation quality

---

## About Me

I am currently learning and developing skills in cybersecurity and SOC analysis.  
This project is part of my professional learning journey focused on Blue-Team practices, security monitoring, and incident response operations.

If you have feedback or would like to connect — I’m always happy to learn more 
