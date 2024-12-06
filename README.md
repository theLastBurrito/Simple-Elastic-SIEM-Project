# **Elastic SIEM Home Lab Project**

## **Project Objective**  
The aim of this project is to establish a practical home lab using the Elastic Stack Security Information and Event Management (SIEM) platform and a Kali Linux virtual machine (VM). The lab focuses on generating and analyzing security events, configuring data forwarding through an agent, and utilizing Elastic's powerful querying capabilities. Additionally, it involves creating interactive dashboards and setting up alerts for security monitoring. This hands-on experience is an excellent addition to a resume and serves as a discussion point in interviews.
## **Tools Used**  
- **Elastic Stack (SIEM)**: A platform for collecting, analyzing, and visualizing security data.  
- **Kali Linux VM**: A penetration testing OS to simulate security events.  
- **VirtualBox**: A virtualization platform to host the Kali Linux VM.  
## **Skills Gained**  
- Setting up and using the Elastic SIEM for security monitoring.  
- Installing and configuring Elastic Agents on Linux-based endpoints.  
- Generating and analyzing security events using Elastic Stack tools.  
- Creating dashboards and alerts for proactive security monitoring.  

---

## **Steps**  

### **Task 1: Setting up the Elastic SIEM Environment**  
- Sign up to use Elastic Cloud at Elastic Cloud.
- Log in to the Elastic Cloud console.
- Click on Start your free trial.
- Click on the Create Deployment button and select Elasticsearch as the deployment type.
- Choose a region and deployment size that fits your needs and click on Create Deployment.
- Wait for the configuration to complete.
- Once the deployment is ready, click Continue.
### **Task 2 : Installing and Configuring the Elastic Agent**  
An agent is a software program that is installed on a device, such as a server or endpoint, to collect and send data to a centralized system for analysis and monitoring. In the context of Elastic SIEM, an agent is used to collect and forward security-related events from your endpoints to your Elastic SIEM instance.
- Log in to Elastic SIEM instance and navigate to the Integrations page
- Clicking on the Kibana main menu bar at the top left
- Selecting “Integrations” at the bottom.
  
<img src="https://github.com/user-attachments/assets/e02e0dfe-fc05-432f-b757-78e715c72268" alt="Description" width="500">

- Search for “Elastic Defend” and click on it to open the integration page
  
<img src="https://github.com/user-attachments/assets/f1aff8fb-746a-4a06-88b8-f46a84cf1c48" alt="Description" width="500>

- Click on “Install Elastic Defend” and follow the instructions provided on the integration page to install the agent on Kali VM.
  
<img src="https://github.com/user-attachments/assets/fefbd8af-ac28-4cc2-8cf3-c35ebc7153e8" alt="Description" width="500>

<img src="https://github.com/user-attachments/assets/c730649d-5800-4fc6-ab58-ab0bace145d9" alt="Description" width="500>

- Paste that command into the Kali terminal

<img src="https://github.com/user-attachments/assets/808257a8-12a2-4909-82a4-e38ed2ef052d" alt="Description" width="500>

- Once the agent is installed, it will say “Elastic Agent has been successfully installed.” It will automatically start collecting and forwarding logs to Elastic SIEM instance

<img src="https://github.com/user-attachments/assets/bd1ddc03-e618-41ac-b57a-f9fff6b74a5b" alt="Description" width="500>

- Verify that the agent has been installed correctly by running this command: sudo systemctl status elastic-agent.service

<img src="https://github.com/user-attachments/assets/1262e6a5-1fda-414c-a086-124888084f38" alt="Description" width="500>

### **Task 3 : Generating Security Events on the Kali VM**
To confirm the agent's functionality, I used Nmap on my Kali VM. This open-source tool scans networks to identify open ports, detect operating systems, and gather key network information.
- Run a scan on Kali machine by running the command: sudo nmap <vm-ip>.
  
<img src="https://github.com/user-attachments/assets/c04c6966-dbf2-4265-9723-7dd66a5c17d1" alt="Description" width="500>
