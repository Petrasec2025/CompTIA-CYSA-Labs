
# 🛡️ Assisted Lab: Configuring Controls (Topic 2.2 – CySA+)

## 📘 Overview

This lab focused on applying **Corrective**, **Preventive**, and **Directive** security controls in a Windows Server 2019 enterprise environment. Acting as a cybersecurity analyst at *Structureality Inc.*, I used PowerShell scripting and built-in administrative tools to identify, implement, and validate controls that reduce organizational risk.

This hands-on lab simulated real-world SOC analyst activities including:
- System fault simulation
- File integrity monitoring
- Access restriction configuration
- User behavior guidance via system banners

---

## 🎯 Objectives

- Understand and apply different control types:
  - ✅ **Corrective** – Restore systems to a secure state
  - ✅ **Preventive** – Block unauthorized access before it occurs
  - ✅ **Directive** – Inform users about acceptable behavior and compliance
- Use PowerShell to calculate and verify file hashes (SHA256)
- Restrict network share permissions to authorized users only
- Configure system login banners with legal and compliance notices

---

## 🧪 Key Tasks & Implementations

### 🔧 Corrective Controls
- Simulated a system crash using `NotMyFault64` to observe system behavior.
- Created `notes.txt` and generated a SHA256 hash for integrity monitoring.
- Wrote PowerShell scripts (`calchash.ps1` and `check.ps1`) to:
  - Save baseline hashes
  - Detect tampering
  - Restore the file from `notes_backup.txt` automatically

### 🛡 Preventive Controls
- Removed `Everyone` group access from the `\\10.1.16.1\CertEnroll` share.
- Confirmed restricted access using test login as user `Rene`.
- Demonstrated enforcement of **least privilege** principles.

### 📢 Directive Controls
- Used PowerShell to set registry keys:
  - `legalnoticecaption`
  - `legalnoticetext`
- Verified banner displayed upon system login, aligning with GDPR and acceptable use policies.

---

## 🧰 Tools & Utilities Used

| Tool/Utility            | Purpose                                      |
|-------------------------|----------------------------------------------|
| **PowerShell**          | File integrity, access control, registry edits |
| **NotMyFault64**        | System crash simulation                      |
| **Windows Registry**    | Login banner configuration                   |
| **MMC (Computer Mgmt)** | Share and user access management             |

---

## 🎓 CySA+ Exam Objectives Mapped

| Domain | Description                                                        |
|--------|--------------------------------------------------------------------|
| **1.1** | Apply cybersecurity concepts to system and network architecture   |
| **2.1** | Implement security solutions to manage risks                      |
| **2.2** | Execute controls and countermeasures to mitigate vulnerabilities  |
| **2.5** | Respond to and recover from vulnerabilities and misconfigurations |

---

## 🗂️ Repository Contents
```bash
2.2-Assisted-Lab-Configuring-Controls/
├── README.md        # Lab summary and documentation
└── notes.md         # Detailed steps, commands, and reflections
