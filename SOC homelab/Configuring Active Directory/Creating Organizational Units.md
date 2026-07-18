# Overview
- This section will feature the creation of Orgnanizational Units (OUs) using powershell. Additionally, I will also create several accounts to simulate a small firm


# Creating Organizational Units
- I utilized Microsoft's powershell page to configure the OUs
- Direct link: https://learn.microsoft.com/en-us/powershell/module/activedirectory/new-adorganizationalunit?view=windowsserver2025-ps


- This command creates a OU called **Servers**
<img width="1008" height="25" alt="image" src="https://github.com/user-attachments/assets/ba9c1970-aa3d-46f9-b8d5-eaacfb1a3631" />

- I also created an OU called **Workstations**

<img width="752" height="41" alt="image" src="https://github.com/user-attachments/assets/15009bbf-adc7-4443-98de-1cc01f62516d" />

- This view shows the OU in the Active Directory Users and Computers"

<img width="512" height="352" alt="image" src="https://github.com/user-attachments/assets/0c1c9f41-e82a-449a-a5d8-17c04c4550a2" />


- I first moved the Suricata sever to the Custom Organizational Unit: **Servers**

<img width="1025" height="375" alt="image" src="https://github.com/user-attachments/assets/dc18663e-6a2f-4d31-aa98-7dc9175868c2" />

- I also moved the Splunk server to the **Servers** OU

<img width="1012" height="25" alt="image" src="https://github.com/user-attachments/assets/8e91b990-6b04-4487-91b0-00b64eb76bb7" />

- We can see the moved Splunk server in the **Servers** OU
