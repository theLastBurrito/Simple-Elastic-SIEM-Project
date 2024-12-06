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
