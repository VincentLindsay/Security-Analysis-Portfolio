# Summary
- This section involves the promotion of the Windows Server 2019 into a Domain Controller (DC).

# Promoting the server to a Domain Controller
- Prior to the installation of Active Directory Domain Services (AD-DS), I assigned the server a static IP and DNS IP adresses.
- To do this, I navigated to the network adapter's settings on the machine.

<img width="810" height="615" alt="image" src="https://github.com/user-attachments/assets/44a5ec4d-9107-48a5-b006-a87314ac9b4b" />

- I also changed the NIC of the vm to have the custom made VNET I made previously

- To be able to promote the server, AD-DS has to be installed.
- This was done by the addition of roles and features
