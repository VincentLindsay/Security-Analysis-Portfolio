# Overview

- This attack will be a multi-stage simulated attack that follows the MITRE ATT&CK framework TTPs of:
    - **Reconnaisance** by:
    - Network Scanning — T1595 — Attacker performs a ping sweep and full‑port Nmap scan on 172.16.50.0/24
    - Service Enumeration — T1046 — Attacker identifies Kerberos, LDAP, RDP on 172.16.50.10
    - LDAP Banner Grabbing — T1040 — Attacker uses Netcat to pull LDAP banners and confirm domain name
 
    - **Credential Access** via:
    - Kerberos Username Enumeration — T1087 — Kerbrute probes valid AD usernames
    - AS‑REP Roasting — T1556.004 — Attacker requests AS‑REP tickets for accounts without preauthentication
    - Kerberoasting — T1558.003 — Attacker requests TGS tickets for SPN accounts
    - Password Cracking — T1110.002 — Hashcat cracks AS‑REP and Kerberoast hashes

    - **Lateral Movement** by:
    - Using Valid Accounts — T1078 — Attacker uses cracked credentials (Privileged accounts)
    - RDP Lateral Movement — T1021.001 — Attacker uses xfreerdp to access DC01$
 
    - **Privilege Escalation**
    - Create Account — T1136.001 — Attacker creates adm‑backdoor
    - Privilege Escalation via Group Membership — T1078 — Attacker adds adm‑backdoor to Domain Admins
    - Modify Registry — T1112 — Attacker hides the backdoor account via registry changes
 
    - **Collection**
    - File Collection — T1005 — Attacker compresses C:\Users into a ZIP archive
    - Archive Collected Data — T1074 — Attacker uses Compress‑Archive to stage data
 
    - **Exfiltration**
    - Exfiltration Over SSH — T1048.003 — Attacker uses SCP to pull ZIP file from DC
    - Exfiltration Over Network — T1041 — Outbound connection from DC to attacker machine
 
    - Defense Impairment
    - Clear Windows Event Logs — T1685.005 — Attacker clears Security logs using
