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
