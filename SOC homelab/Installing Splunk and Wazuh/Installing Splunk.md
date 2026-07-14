# Overview
- This section involves the installation and configuration of Splunk. The configuration will be similar to the [Splunk lab](https://github.com/VincentLindsay/Security-Analysis-Portfolio/tree/main/Splunk%20lab) I've completed previously.

<img width="1632" height="841" alt="image" src="https://github.com/user-attachments/assets/62a4e68a-b565-4693-9ff5-3a022dc818cd" />


# Installing Splunk
- To install Splunk, you will need to navigate to Splunk's webpage.
- link: https://www.splunk.com/
- Create an account if you do not have one.
- Once logged in, click Trials and Downloads.

<img width="1862" height="291" alt="image" src="https://github.com/user-attachments/assets/8aa10268-ed8f-422b-aca2-6ca7d0655440" />

- Click on Splunk Enterprise trial

<img width="1397" height="657" alt="image" src="https://github.com/user-attachments/assets/f1b11b5f-3a1a-4295-bb1c-08bc580b8ce2" />

- Select the installation package for Linux, and specifically the .deb package since we are using Ubuntu, which is a distribution of Debian Linux.

<img width="1647" height="832" alt="image" src="https://github.com/user-attachments/assets/ced5d4c3-4974-4cc3-9bf9-4802f71544f6" />

- Since we are SSH'd into the server, we can simply copy the wget link.
- After retrieving the package, we can see that it is present in the server.

<img width="1918" height="437" alt="image" src="https://github.com/user-attachments/assets/d0a430a4-6345-4f02-a1d3-0fa6a5af5750" />

- Next, I began to install the package to the Splunk server.

<img width="1307" height="232" alt="image" src="https://github.com/user-attachments/assets/6e95c6f7-0e84-4127-8afb-6c414cdb9cfa" />


- After I installed the package, I navigated to the /opt/splunk/bin directory to install Splunk onto the server.
- In the directory, I logged into the splunk account using **sudo -u splunk bash**, and began to run the installer.

<img width="1542" height="256" alt="image" src="https://github.com/user-attachments/assets/225b78f4-60b3-429f-a42b-9b9072396879" />

- Agree to the license, and create an administrator account that will be used to login to the console.
- Once you agree, the installation of Splunk will begin.

<img width="1271" height="123" alt="image" src="https://github.com/user-attachments/assets/f8553f03-01ee-4dc9-b4d8-d6f483577ae3" />

- I also configured the Splunk account and service to always lauch on boot.
- I also created a snapshot of when splunk was installed

- I was able to login to the splunk console from my host machine using the server's IP address on port 8000
<img width="1915" height="992" alt="image" src="https://github.com/user-attachments/assets/3e6edd32-2812-4935-9f17-726ba32017de" />





  
