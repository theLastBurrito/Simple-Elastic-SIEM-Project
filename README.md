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
  
<img src="https://github.com/user-attachments/assets/f1aff8fb-746a-4a06-88b8-f46a84cf1c48" alt="Description" width="500">

- Click on “Install Elastic Defend” and follow the instructions provided on the integration page to install the agent on Kali VM.
  
<img src="https://github.com/user-attachments/assets/fefbd8af-ac28-4cc2-8cf3-c35ebc7153e8" alt="Description" width="500">
<br>
<img src="https://github.com/user-attachments/assets/c730649d-5800-4fc6-ab58-ab0bace145d9" alt="Description" width="500">

- Paste that command into the Kali terminal

<img src="https://github.com/user-attachments/assets/808257a8-12a2-4909-82a4-e38ed2ef052d" alt="Description" width="500">

- Once the agent is installed, it will say “Elastic Agent has been successfully installed.” It will automatically start collecting and forwarding logs to Elastic SIEM instance

<img src="https://github.com/user-attachments/assets/bd1ddc03-e618-41ac-b57a-f9fff6b74a5b" alt="Description" width="500">

- Verify that the agent has been installed correctly by running this command: sudo systemctl status elastic-agent.service

<img src="https://github.com/user-attachments/assets/1262e6a5-1fda-414c-a086-124888084f38" alt="Description" width="500">

### **Task 3 : Generating Security Events on the Kali VM**
To confirm the agent's functionality, I used Nmap on my Kali VM. This open-source tool scans networks to identify open ports, detect operating systems, and gather key network information.
- Run a scan on Kali machine by running the command: sudo nmap <vm-ip>.
  
<img src="https://github.com/user-attachments/assets/c04c6966-dbf2-4265-9723-7dd66a5c17d1" alt="Description" width="500">

- This scan generates several security events, such as the detection of open ports and the identification of services running on those ports. Run a few more Nmap scans (“nmap -sS <ip address>”, “nmap -sT <ip address>”, “nmap -p- <ip address>”etc..”

<img src="https://github.com/user-attachments/assets/1b2d9d48-22f5-4cd7-9c5a-224ebc4f97ff" alt="Description" width="500">

### **Task 4 : Querying for Security Events in the Elastic SIEM**
With data forwarded from the Kali VM to the SIEM, I began querying and analyzing the logs.
- Inside Elastic Deployment, click on the menu icon at the top-left with the three horizontal lines and then click on the “Logs” tab under “Observability” to view the logs from the Kali VM.

<img src="https://github.com/user-attachments/assets/87c01544-f3d1-4995-bb22-f4beadd058af" alt="Description" width="500">

- In the search bar, enter a search query to filter the logs. For example, to search for all logs related to Nmap scans, enter the query: event.action:
“nmap_scan” or process.args: “sudo”.
- Click on the “Search” button to execute the search query.
- The results of the search query will be displayed in the table below. Click on the three dots next to each event to view more details.

<img src="https://github.com/user-attachments/assets/9af1c0fe-6c5f-4c2f-8548-fc906dfe1c5d" alt="Description" width="500">
<br>
<img src="https://github.com/user-attachments/assets/348e6a5b-8830-4811-9608-390a1847183c" alt="Description" width="500">


By generating and analyzing various security events in Elastic SIEM, such as authentication failures or incorrect SSH login attempts, I gained valuable insights into detecting, investigating, and responding to security incidents in real-world scenarios.

### **Task 5 : Create a Dashboard to Visualize the Events**
I utilized visualizations and dashboards in the SIEM app to analyze logs, identify patterns, and detect anomalies, including creating a dashboard to track security events over time.
- Navigate to the Elastic web portal at https://cloud.elastic.co/.
- Click on the menu icon on the top-left, then under “Analytics,” click on “Dashboards.”

<img src="https://github.com/user-attachments/assets/f8b6cce0-1b13-4c8d-b753-049c768bd4ed" alt="Description" width="500">

- Click on the “Create dashboard” button on the top right to create a new dashboard.

- Click on the “Create Visualization” button to add a new visualization to the dashboard.

- Select “Area” type. This will create a chart that shows the count of events over time.

<img src="https://github.com/user-attachments/assets/7113ccbf-7f2e-47d5-bcc3-325c5c899555" alt="Description" width="500">

- In the “Metrics” section of the visualization editor on the right, select “Count” as the vertical field type and “Timestamp” for the horizontal field. This will show the count of events over time.

<img src="https://github.com/user-attachments/assets/7f306c4d-efd2-4237-9094-2043cb6453cc" alt="Description" width="500">
<br>
<img src="https://github.com/user-attachments/assets/3e396a64-a3f3-474e-aead-efae495c9110" alt="Description" width="500">
<br>
<img src="https://github.com/user-attachments/assets/61773b79-345f-4b33-8d5e-bbc95fe6385b" alt="Description" width="500">
<br>
- Click on the “Save” button to save the visualization and then complete the rest of the settings.

<img src="https://github.com/user-attachments/assets/985c2873-857a-472e-9e06-3557c88c6517" alt="Description" width="500">

### **Task 6 : Create an Alert**
Alerts are essential in a SIEM for detecting and responding to security incidents promptly. They are based on predefined rules or custom queries and can trigger specific actions when conditions are met. In this task, I created an alert in Elastic SIEM to detect Nmap scans, enabling continuous monitoring of logs and notifications when such events are detected.
- Click on the menu icon on the top-left, then under “Security,” click on “Alerts.”
- Click on “Manage rules” at the top right.

<img src="https://github.com/user-attachments/assets/60660916-3315-4099-a151-9602ba825f2c" alt="Description" width="500">

- Click on the “Create new rule” button at the top right.
- Under the “Define rule” section, select the “Custom query” option from the dropdown menu.
- Under “Custom query,” set the conditions for the rule. You can use the following query to detect Nmap scan events.

<img src="https://github.com/user-attachments/assets/5e06f9e9-0332-4a4e-aa18-17b064edee0d" alt="Description" width="500">

- This query will match all events with the action “nmap_scan.” Then click “Continue.”
- Under the “About rule” section, give your rule a name and a description (Nmap Scan Detection).
- Set the alert's severity level to prioritize its importance. Leave the default settings under “Schedule rule” unchanged, then click “Continue.”

<img src="https://github.com/user-attachments/assets/6b49a994-48b6-4d0c-b3d8-6f10860c9053" alt="Description" width="500">

- In the “Actions” section, choose the desired response for the triggered rule, such as sending an email, posting a Slack message, or activating a custom webhook.
- Finally, click the “Create and enable rule” button to create the alert.

<img src="https://github.com/user-attachments/assets/1f83db7f-e0ff-450e-ba20-f724be59b622" alt="Description" width="500">

- After creating the alert, it will actively monitor your logs for Nmap scan events. If such an event is detected, the alert will trigger and execute the configured action. You can manage and review your alerts in the “Alerts” section under “Security.”
