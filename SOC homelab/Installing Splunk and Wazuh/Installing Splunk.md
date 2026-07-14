# Overview
- This section involves the installation and configuration of Splunk. The configuration will be similar to the [Splunk lab](https://github.com/VincentLindsay/Security-Analysis-Portfolio/tree/main/Splunk%20lab) I've completed previously.

<img width="1632" height="841" alt="image" src="https://github.com/user-attachments/assets/62a4e68a-b565-4693-9ff5-3a022dc818cd" />


# Installing Splunk
- To install Splunk, you will need to navigate to Splunk's webpage
- link: https://www.splunk.com/
- Create an account if you do not have one.
- Once logged in, click Trials and Downloads

<img width="1862" height="291" alt="image" src="https://github.com/user-attachments/assets/8aa10268-ed8f-422b-aca2-6ca7d0655440" />

- Click on Splunk Enterprise trial

<img width="1397" height="657" alt="image" src="https://github.com/user-attachments/assets/f1b11b5f-3a1a-4295-bb1c-08bc580b8ce2" />

- Select the installation package for Linux, and specifically the .deb package since we are using Ubuntu, which is a distribution of Debian Linux

<img width="1647" height="832" alt="image" src="https://github.com/user-attachments/assets/ced5d4c3-4974-4cc3-9bf9-4802f71544f6" />

- Since we are SSH'd into the server, we can simply copy the wget link
- After retrieving the package, we can see that it is present in the server

<img width="1918" height="437" alt="image" src="https://github.com/user-attachments/assets/d0a430a4-6345-4f02-a1d3-0fa6a5af5750" />

- Next, I began to install the package to the Splunk server


- After I installed the package, I navigated to the /opt/splunk/bin directory to further configure the instance
- In the directory, I logged into the splunk account using **sudo -u splunk bash**, and began to run the installer 


  
