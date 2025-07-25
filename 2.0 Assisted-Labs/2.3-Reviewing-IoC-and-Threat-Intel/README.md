# 🔍 Lab 2.3 – Reviewing IoC and Threat Intelligence Sources

📁 **Lab Path**: `1.4 Threat Intelligence & Threat Hunting`  
🧑‍💻 **Author**: Petras Guilherme Kulyumba  
🗓️ **Date Completed**: 07/25/2025  
💻 **VM**: `PC10` – Windows Server 2019

---

## 🎯 Objective

Gain practical experience in:

- Reviewing public IoC feeds and threat intelligence sources  
- Using exploit and vulnerability databases  
- Customizing security policy templates (SANS)  
- Navigating CIS configuration benchmarks  

---

## 📘 Key Concepts

**Indicator of Compromise (IoC):**  
Artifacts that signal a potential compromise: IPs, Domains, URLs, File Hashes, Hostnames

**Threat Intelligence:**  
Evidence-based information to detect, prevent, and respond to cyber threats

**Exploit:**  
A technique or code that takes advantage of a vulnerability

**Google Dork:**  
Advanced search operators for identifying publicly exposed sensitive data

---

## 🧪 Tasks Overview

### 1. Real-Time IoC Feeds – CIS MS-ISAC  
[https://www.cisecurity.org/ms-isac/services/real-time-indicator-feeds](https://www.cisecurity.org/ms-isac/services/real-time-indicator-feeds)  

![CIS Feed Intro](https://github.com/user-attachments/assets/e12bb78c-065e-44f2-bd55-20cf582e9057)

---

### 2. IoC Analysis – AlienVault OTX  
[https://otx.alienvault.com/browse/global/pulses](https://otx.alienvault.com/browse/global/pulses)  
Searched for `mirai`, `domain`, `ipv4`, `hostname`, etc.

![AlienVault Home](https://github.com/user-attachments/assets/1e6c85e5-1e38-42f7-98b1-68e14a254fef)  
![Search Filters](https://github.com/user-attachments/assets/6be07ae9-bb81-4295-b00c-dc8041a8ec4e)  
![IoC Pulse Results](https://github.com/user-attachments/assets/e0fba94b-ac5d-4c5b-8bfa-acfe48c461ea)

---

### 3. Exploit-DB + Google Hacking Database  
[https://www.exploit-db.com/](https://www.exploit-db.com/)  
Explored exploit types, platforms, and the GHDB category “Files Containing Passwords”

![Exploit Search](https://github.com/user-attachments/assets/dc4897d7-7db8-48ac-997f-be6f9c73699a)  
![GHDB Category](https://github.com/user-attachments/assets/5d5a14ea-68c9-4e26-9f09-0b97f778bcf0)

---

### 4. SANS Policy Template Customization  
[https://www.sans.org/information-security-policy/](https://www.sans.org/information-security-policy/)  
Edited the **Web Application Security Policy**  
🔁 Replaced `<Company Name>` → `CySA+ Lab Corp`  
💾 Saved as: `Web_App_Security_Policy_v.1.1.doc`

![Policy Editing](https://github.com/user-attachments/assets/ada9bd55-fa82-41c6-a648-ac96b6d2dd74)

---

### 5. CIS Security Benchmarks  
[https://www.cisecurity.org/cis-benchmarks/](https://www.cisecurity.org/cis-benchmarks/)  
Benchmarks found: ✅ Firefox, ✅ AWS, ✅ Docker, ❌ Discord

![Search Benchmarks](https://github.com/user-attachments/assets/87e80aee-1fe9-4ac5-b99a-4a6a2fe4172a)  
![Valid Benchmarks](https://github.com/user-attachments/assets/4e09ba51-3e45-4598-ae33-898181f021f2)  
![Discord Missing](https://github.com/user-attachments/assets/ca0d8909-0942-4477-a87e-ed5d88b789a3)

---

## ✅ Assessment Answers

| Question                        | Answer                       |
|--------------------------------|------------------------------|
| Purpose of IoCs?               | Detect violations            |
| Threat feed sources?           | Gov, Commercial, OSS         |
| AlienVault indicators?         | Domain, URL, IPv4, etc.      |
| Exploit-DB uniqueness?         | Source code                  |
| Google Dork?                   | Advanced search query        |

---

## 📌 Completion Checklist

- [x] Accessed CIS real-time feeds  
- [x] Explored AlienVault IoCs  
- [x] Reviewed Exploit-DB and GHDB  
- [x] Customized SANS policy  
- [x] Navigated CIS Benchmarks  

---

## 🧾 Summary

This lab enhanced hands-on threat intelligence skills through:

- IoC identification and analysis  
- Searching live threat feeds and exploit databases  
- Documenting security controls via SANS templates  
- Applying benchmark best practices for hardening  

---

## 📂 Files

- `Web_App_Security_Policy_v.1.1.doc` – Customized SANS policy document

---

## 📸 Final Evidence Snapshot

![Checklist](https://github.com/user-attachments/assets/d4eda63f-30f7-49d4-80f9-9acb3501924d)

---

## 💬 Commit Tip

```bash
git add .
git commit -m "📘 Add Lab 2.3 – IoC and Threat Intel: README, screenshots, and customized SANS policy"
git push


