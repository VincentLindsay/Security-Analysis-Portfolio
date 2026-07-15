# Summary
- This section features the installation of Zeek onto the Ubuntu server on verion 24.04.

# Installing Zeek
- Similar to the installation of Splunk, I also configured the server's IP address to be static, with an additional NIC for external connectivity.
<img width="961" height="322" alt="image" src="https://github.com/user-attachments/assets/8473e37c-2189-472b-bce9-672c9d2aa7db" />

- The configurations are similar, except the IP address is assigned for the server as **172.16.50.50/24**

<img width="918" height="550" alt="image" src="https://github.com/user-attachments/assets/c8031404-cc2e-4faa-9bde-4737be2cb907" />

- Upon verifying connectivity, I can see that the configurations were successful.

- To install zeek, I obtained the packages from the zeek project's installation page
- Direct link: https://docs.zeek.org/en/current/install.html

<img width="936" height="528" alt="image" src="https://github.com/user-attachments/assets/55d69bf2-e8d4-4e12-a305-9a31bc43dd8f" />

- Select the latest release, and click sources.
<img width="1918" height="393" alt="image" src="https://github.com/user-attachments/assets/e6aba3df-d742-47ad-a4be-41b6aa8c0680" />

- It will take you to the page shown in the above screenshot.
- Since I am using Ubuntu version 24.04, I will add the repository, and install manually.
- The commands will install Zeek onto the server
- For the post-fix configuaration, I chose "No configuration"
<img width="1006" height="713" alt="image" src="https://github.com/user-attachments/assets/66848e98-9629-47e6-af23-403eeae77152" />

- After sometime, Zeek was installed onto the server.

