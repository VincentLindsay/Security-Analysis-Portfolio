# Overview
This section involves the installation and configuration of a Windows 10 endpoint to serve as the victim machine in a later simulated attack.

# Steps taken
- To retrieve the ISO for Windows 10, I searched the web for "download windows 10".
- Direct link: https://www.microsoft.com/en-us/software-download/windows10
- I chose the option to download an ISO file.
  
<img width="1317" height="582" alt="image" src="https://github.com/user-attachments/assets/5a30635c-fbdf-4e19-bea5-8285acd9287b" />

- After sometime, I created the virtual machine, and disabled side channel mitigations for additional performance.
- I will eventually add Splunk Universal Forwarder, and Sysmon to this vm.
- I will also add this machine to the domain I created.

<img width="707" height="562" alt="image" src="https://github.com/user-attachments/assets/2c1ab86d-1025-4b0d-8878-af9a18ce55f4" />

- Since I do not have a product key, I chose the option of "I don't have a product key."
- I selected Windows 10 Pro as the edition of Windows for this homelab.
- After sometime, the vm reached the set up phase of Windows.
<img width="927" height="666" alt="image" src="https://github.com/user-attachments/assets/734459ac-9007-4c07-8971-b089ad19ff3d" />

- I chose the "Set Up for Work or School" option because I can create a local account, and Domain join later.
<img width="922" height="666" alt="image" src="https://github.com/user-attachments/assets/74dad58b-ace4-45e4-acc5-c86f62cf2123" />

- For the name of the user account, I named it my name: Vincent.
- Once logged in, I began to optimise the performance of the vm, and I disabled Windows Updates via group policy edit.
- I also disabled Widgets, and background apps.
<img width="685" height="632" alt="image" src="https://github.com/user-attachments/assets/4feb8234-b53b-4613-93de-e6a7407eb548" />

- Now the Windows machine is in a good state to configure Sysmon, and Splunk universal forwarder.



