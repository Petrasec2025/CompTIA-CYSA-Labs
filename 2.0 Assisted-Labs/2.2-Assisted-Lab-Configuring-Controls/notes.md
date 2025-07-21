# Lab Notes: Configuring Security Controls

## Corrective Controls

**Goal**: Restore a secure state after a change or failure.

### Steps:
1. Ran `notmyfault64` to trigger a BSOD (Windows crash).
2. Confirmed Windows native corrective action resets the system and halts the faulty app.
3. Created `notes.txt` with content `"This is important"`.
4. Hashed the file content using:
   ```powershell
   Get-FileHash ./notes.txt -Algorithm SHA256 | Select-Object -ExpandProperty Hash | Set-Content ./hash.txt
   ```
5. Simulated file tampering:
   ```powershell
   echo blah >> notes.txt
   ```
6. Compared file hash and restored original content manually.
7. Automated detection and repair via PowerShell scripts:
   - `calchash.ps1`: saves hash
   - `check.ps1`: compares hash and restores if needed

✅ **Detection Method**: File integrity via SHA256 hashing.

---

## Preventive Controls

**Goal**: Block access before unauthorized action occurs.

### Steps:
1. Discovered non-admin access to `\\10.1.16.1\CertEnroll`.
2. Logged into `DC10`, removed `Everyone` group from share permissions.
3. Validated access as user `Rene` was denied.

✅ **Key Principle**: Least privilege enforcement.

---

## Directive Controls

**Goal**: Guide or influence user behavior through instruction.

### Steps:
1. Configured login banner via PowerShell:
   ```powershell
   New-ItemProperty -Path "HKLM:\Software\Microsoft\Windows\CurrentVersion\Policies\System" -Name "legalnoticecaption" -Value "Authorized Use Only" -PropertyType "String" -Force
   New-ItemProperty -Path "HKLM:\Software\Microsoft\Windows\CurrentVersion\Policies\System" -Name "legalnoticetext" -Value $BannerText -PropertyType "String" -Force
   ```
2. Verified banner appeared on login screen.
3. Communicated compliance and acceptable use.

---

## Summary

| Control Type | Example Implemented                        | Purpose                                   |
| ------------ | ------------------------------------------ | ----------------------------------------- |
| Corrective   | PowerShell script to restore file content  | Restore secure state                      |
| Preventive   | Share permission restriction on CertEnroll | Block unauthorized access                 |
| Directive    | Legal warning login banner                 | Guide user behavior and ensure compliance |
----
## 📸 Screenshots

<details>
<summary><strong>🛠️ Corrective Controls</strong></summary>

<br>

<img src="https://github.com/user-attachments/assets/4f97b8b7-b742-4453-b8cd-179fefc936a6" width="800" alt="BSOD using notmyfault64">
<img src="https://github.com/user-attachments/assets/73a7edc5-c49a-4626-b698-d31e2ce001bf" width="800" alt="Windows auto-recovery">
<img src="https://github.com/user-attachments/assets/4aee250e-f5e9-4235-bc1c-d96066b50c65" width="800" alt="Creating and hashing notes.txt">
<img src="https://github.com/user-attachments/assets/8078c5d0-d2f1-49ca-9f61-0575fec4d020" width="800" alt="File tampering simulation">
<img src="https://github.com/user-attachments/assets/b4ba599e-bb73-47f9-a663-baf30ba6dbd2" width="800" alt="PowerShell: Compare & restore hash">
<img src="https://github.com/user-attachments/assets/6f7cd7b8-36f2-4887-8853-d44e49dff3ae" width="800" alt="Hash validation complete">

</details>

---

<details>
<summary><strong>🔒 Preventive Controls</strong></summary>

<br>

<img src="https://github.com/user-attachments/assets/e2caaa0e-36fc-4acb-a52c-3715d20d0aec" width="800" alt="CertEnroll accessed by non-admin">
<img src="https://github.com/user-attachments/assets/229a88de-1d4a-486a-8a6f-fd7320a00c62" width="800" alt="DC10 share permission settings">
<img src="https://github.com/user-attachments/assets/2580bee0-678b-463a-821c-82f1158f2977" width="800" alt="Access denied for user Rene">
<img src="https://github.com/user-attachments/assets/ef78505f-e122-42f3-83f5-760214b2de40" width="800" alt="Access control verification">

</details>

---

<details>
<summary><strong>📢 Directive Controls</strong></summary>

<br>

<img src="https://github.com/user-attachments/assets/3238e5bc-eab7-4043-97e3-01ab8d3b36bd" width="800" alt="Login banner registry configuration">
<img src="https://github.com/user-attachments/assets/8b192cda-0579-4424-8e7c-b838af6b002c" width="800" alt="Legal login banner on display">
<img src="https://github.com/user-attachments/assets/eb75d28d-abe1-482a-8579-196b45aa3cc9" width="800" alt="Login screen validation">

</details>
