# Overview
- This section will feature the creation of alerts that pertain to the simulated attack.


# Creating the alerts
- The first alert I created checks for Kerberos TGT enumeration attempts
<img width="1002" height="907" alt="image" src="https://github.com/user-attachments/assets/93ef07f0-c127-4e30-a073-9bdbcb107576" />

```Bash
index="winevent" (EventCode=4768 OR EventCode=4771)    Account_Name!="DC01$" | stats  count by _time, Account_Name
```

- This alert catches accounts with do not require Kerberos preauthentication enabled.
```Bash
index=winevent EventCode=4768 Account_Name!=DC01$
| where isnull(PreAuthType) OR PreAuthType=0
| stats count by _time, Account_Name, EventCode
```
<img width="1001" height="907" alt="image" src="https://github.com/user-attachments/assets/2d07a41d-7ca4-48f9-983e-05973962815c" />

```Bash
index=winevent EventCode=4769 
| where NOT match(AccountName, ".*\\$") AND AccountName!="krbtgt"
| stats count by _time, Account_Name, Service_Name, Client Address
```
- This alert detects abnormal spikes in TGS requests, but excludes the machine's name from appearing

<img width="1005" height="911" alt="image" src="https://github.com/user-attachments/assets/f7410e3c-d182-405a-b834-3fe8bca93e85" />

- This alert detects when a remote connection is detected from outside of our subnet.
```Bash
index=winevent EventCode=4624 Logon_Type = 10
| where NOT cidrmatch("172.16.50.0/24", Source_Network_Address)
| search NOT Account_Name IN ("SYSTEM","LOCAL SERVICE","NETWORK SERVICE","svc_*")
| table _time host Account_Name Source_Network_Address Workstation_Name
```

# Creating the dashboards
