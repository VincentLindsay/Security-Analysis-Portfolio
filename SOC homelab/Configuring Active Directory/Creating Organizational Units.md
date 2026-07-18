# Overview
- This section will feature the creation of Orgnanizational Units (OUs) using powershell. Additionally, I will also create several accounts to simulate a small firm


# Creating Organizational Units
- I utilized Microsoft's powershell page to configure the OUs
- Direct link: https://learn.microsoft.com/en-us/powershell/module/activedirectory/new-adorganizationalunit?view=windowsserver2025-ps


- This command creates a OU called **Servers**
<img width="1008" height="25" alt="image" src="https://github.com/user-attachments/assets/ba9c1970-aa3d-46f9-b8d5-eaacfb1a3631" />

- I also created an OU called **Workstations**

<img width="752" height="41" alt="image" src="https://github.com/user-attachments/assets/15009bbf-adc7-4443-98de-1cc01f62516d" />

- I created another OU known as **ServiceAccounts**


<img width="792" height="37" alt="image" src="https://github.com/user-attachments/assets/6a443407-6e4b-4427-924e-63f7af3d5a3d" />

- Lastly, I created an OU called **PhoenixAdmins**


<img width="806" height="32" alt="image" src="https://github.com/user-attachments/assets/ef30c0c7-b9b1-4db4-9815-1ec293fb868a" />

- This view shows the OUs in the Active Directory Users and Computers


<img width="1025" height="446" alt="image" src="https://github.com/user-attachments/assets/4f5624a7-b488-49d3-8efc-66a58f997393" />

# Organizing the machines by OU

- I first moved the Suricata sever to the Custom Organizational Unit: **Servers**

<img width="1025" height="375" alt="image" src="https://github.com/user-attachments/assets/dc18663e-6a2f-4d31-aa98-7dc9175868c2" />

- I also moved the Splunk server to the **Servers** OU

<img width="1012" height="25" alt="image" src="https://github.com/user-attachments/assets/8e91b990-6b04-4487-91b0-00b64eb76bb7" />

- We can see the moved Splunk server in the **Servers** OU


<img width="1022" height="397" alt="image" src="https://github.com/user-attachments/assets/11ce3d32-ace6-48ec-a866-8d5bb39badfd" />

- The Windows workstation was also moved to the **Workstations** OU.

<img width="1011" height="52" alt="image" src="https://github.com/user-attachments/assets/29cbeec9-f1ce-4b7e-aef8-026a741bfe00" />


<img width="1027" height="380" alt="image" src="https://github.com/user-attachments/assets/21aaef66-758e-4db5-806c-4a79e6cfc26d" />



