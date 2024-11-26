# **Elastic SIEM Home Lab Project**

## **Project Objective**  
This project demonstrates setting up and using the **Elastic Stack SIEM** to monitor security events from a Kali Linux virtual machine. The lab covers key activities, including:  
- Installing and configuring the **Elastic Agent** to forward logs from the Kali VM to the Elastic SIEM.  
- Generating and analyzing security events.  
- Creating a custom dashboard to visualize data.  
- Setting up an alert to detect specific security incidents.  

By the end of this project, I gained hands-on experience with Elastic SIEM, showcasing skills in log management, event detection, and incident response.

---

## **Tools Used**  
- **Elastic Stack (SIEM)**: A platform for collecting, analyzing, and visualizing security data.  
- **Kali Linux VM**: A penetration testing OS to simulate security events.  
- **VirtualBox**: A virtualization platform to host the Kali Linux VM.  

---

## **Skills Gained**  
- Setting up and using the Elastic SIEM for security monitoring.  
- Installing and configuring Elastic Agents on Linux-based endpoints.  
- Generating and analyzing security events using Elastic Stack tools.  
- Creating dashboards and alerts for proactive security monitoring.  

---

## **Steps**  

### **Task 1: Setting up the Elastic SIEM Environment**  
1. **Create an Elastic Account**:  
   - Sign up for a free trial at [Elastic Cloud](https://cloud.elastic.co/registration).  
   - Log in, click **Start your free trial**, and create a new **Elasticsearch** deployment.  
   - Choose deployment size and region, then wait for it to complete.  

2. **Launch the SIEM Instance**:  
   - Access the deployment and open the **Kibana** dashboard from the Elastic Cloud portal.

---

### **Task 2: Installing Kali Linux on VirtualBox**  
1. **Download the Kali Linux VM**:  
   - Download from [Kali.org](https://www.kali.org/get-kali/#kali-virtual-machines).  

2. **Set Up the VM**:  
   - Import the Kali VM into VirtualBox and start the machine.  
   - Follow the on-screen steps to complete the installation.  
   - Log in using the default credentials (`kali/kali`).  

---

### **Task 3: Installing and Configuring the Elastic Agent**  
1. **Install the Elastic Agent**:  
   - In Kibana, navigate to **Integrations** and install the **Elastic Defend** package.  
   - Select **Linux** as the OS, copy the command provided, and execute it in the Kali terminal.  

   ```bash
   sudo ./elastic-agent install --url=<ELASTIC_CLOUD_URL> --enrollment-token=<TOKEN>
