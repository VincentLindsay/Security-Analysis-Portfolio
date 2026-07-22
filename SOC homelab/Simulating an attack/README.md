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
 
    - **Defense Impairment**
        - Clear Windows Event Logs — T1685.005 — Attacker clears Security logs using wevtutil
     
---

# Conducting the attack
- The first phase will be the conducting of Reconnaisance to verify any active machines in the network
<img width="642" height="107" alt="image" src="https://github.com/user-attachments/assets/16f85095-30c0-403f-9c3f-f1ba36357919" />

- Using fping, we can see that there is three machines active, the 172.16.50.1 IP can be seen as the default gateway.

- Next, nmap will be used to identify the open ports of 172.16.50.10
<img width="592" height="57" alt="image" src="https://github.com/user-attachments/assets/6cf060fa-f4dc-4872-ae66-948b31b4b4b8" />

- The results are as follows
<img width="1125" height="558" alt="image" src="https://github.com/user-attachments/assets/c9ad6a26-5a97-4230-ad93-63f12688df14" />

- Ports 88, 389, 445, and 3389 are open, which means the attack chain can proceed.
<img width="1041" height="277" alt="image" src="https://github.com/user-attachments/assets/a97dfe7c-3727-4a33-b8a3-bbd1207dcfb3" />

- Since we know the name of the domain: **phoenix.local**, we can proceed with enumaration of Active Directory services using kerbrute.
<img width="947" height="347" alt="image" src="https://github.com/user-attachments/assets/23f5ddc8-b5e4-414a-9366-da9f47676d2c" />

- I found 5 valid usernames using enumeration of kerberos.

- Next, I will identify which accounts do not require Kerberos authentication using the user list.
<img width="1142" height="252" alt="image" src="https://github.com/user-attachments/assets/84ec7324-9b00-4460-8443-8fd5fc790452" />

- Now the attacker will attempt to Kerberoast, however this failed, meaning the attacker will have to try a different route.
<img width="1310" height="111" alt="image" src="https://github.com/user-attachments/assets/93a7ba4e-16f6-4ccd-b606-300371be0db6" />

- The attempt at password spraying failed, so I moved onto attempting to brute force accounts
<img width="1107" height="278" alt="image" src="https://github.com/user-attachments/assets/29bbe858-593c-4cf0-9ce4-20654285adaf" />

<img width="1102" height="301" alt="image" src="https://github.com/user-attachments/assets/dbd4f77f-06e4-4fc5-9442-d9c45d191aa5" />

- Brute forcing was successful.
- With the successful brute forcing, I will attempt to connect to the machine using various remote connections.
- Using **crackmapexec**, I found that the account named **Bob** was successful for attempting to connect to via SMB.

<img width="1512" height="87" alt="image" src="https://github.com/user-attachments/assets/bc788f11-8ee0-4b85-b534-42d7e18ed96f" />

- Now the attacker has reached a pivotal point in their attack, being able to access the Domain Controller.

<img width="1612" height="121" alt="image" src="https://github.com/user-attachments/assets/e8dbee07-ddca-439a-8e43-ad347a3af956" />

- Now we will attempt to remotely access the Domain Controller.
<img width="1127" height="77" alt="image" src="https://github.com/user-attachments/assets/d3c462f9-45b6-4a82-9ce4-4ae98bd78505" />


