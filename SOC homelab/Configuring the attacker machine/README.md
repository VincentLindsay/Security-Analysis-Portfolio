# Overview
- This section involves the installation of several tools to conduct the simulated attack.

# Configuring the attacker machine
- The the following table shows the attacker's toolkit, mapped by the MITRE ATT&CK framework.


| Category                     | Tools                                                                 | MITRE ATT&CK Technique – ID                                      |
|------------------------------|-----------------------------------------------------------------------|-------------------------------------------------------------------|
| Reconnaissance               | Nmap, Netcat, DNSutils                                                | Active Scanning — T1595<br>Network Service Scanning — T1046<br>DNS Enumeration — T1590.004 |
| Active Directory Enumeration | Kerbrute, ldap-utils, BloodHound, SharpHound                          | Account Discovery — T1087<br>Remote System Discovery — T1018<br>Permission Groups Discovery — T1069<br>Domain Trust Discovery — T1482 |
| Credential Access            | Impacket (GetNPUsers, GetUserSPNs), Hashcat, Responder                | AS‑REP Roasting — T1556.004<br>Kerberoasting — T1558.003<br>Password Cracking — T1110.002<br>LLMNR/NBT‑NS Poisoning — T1557.001 |
| AD Attack Path Mapping       | BloodHound, SharpHound                                                | Permission Groups Discovery — T1069.002<br>ACL Discovery — T1069.001<br>Account Discovery — T1087 |
| Lateral Movement             | xfreerdp (RDP), SSH                                                   | Remote Services (RDP) — T1021.001<br>Remote Services (SSH) — T1021.004<br>Valid Accounts — T1078 |
| Privilege Escalation         | net user / net group                                                  | Create Account — T1136.001<br>Privilege Escalation via Valid Accounts — T1078 |
| Defense Evasion              | Registry modification, SharpHound, Responder                          | Modify Registry — T1112<br>Obfuscated/Encrypted Payloads — T1027<br>Spoofing — T1557 |
| Collection                   | zip/7zip                                                              | Archive Collected Data — T1074<br>File Collection — T1005 |
| Exfiltration                 | SCP/OpenSSH, curl, wget                                                | Exfiltration Over SSH — T1048.003<br>Exfiltration Over Web — T1041 |
| Command & Control            | Netcat, SSH                                                            | Unencrypted C2 — T1095<br>Encrypted C2 — T1573 |

- I will show how I configured the tools for the attack simulation.
