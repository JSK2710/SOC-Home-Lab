## **Requirements:**

- Install [Ubuntu](https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox#1-overview) in VirtualBox
- With 4GB RAM, 2 CPU’s and a minimum of 50GB Storage

# **Installing Wazuh**

### **Step 1:Update the system**

Open the terminal and run these commands.

```
sudo su
```

```bash
apt update && apt upgrade -y
```

### **Step 2:Download the Wazuh installation assistant**

```
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh
```

### **Step 3: Install Wazuh Components**

```
bash ./wazuh-install.sh -a
```

After the installation in the terminal, the user and password for the web interface are displayed.

### **Step 4: Start the Wazuh Services**

```
systemctl daemon-reload
systemctl restart wazuh-indexer
systemctl restart wazuh-manager
systemctl restart wazuh-dashboard
```

### **Step 5: Get the wazuh-dashboard-ip**

To get the IP address of the Wazuh server.

```
ifconfig
```

### **Step 6: Access the Wazuh Web Interface**

Open a web browser and access the Wazuh web interface using the URL: https://<wazuh-dashboard-ip>.

![image.png](attachment:9a4a2cbf-f96c-4b5a-a0c2-79ad3017f814:image.png)

# **Link References:**

Wazuh Documentation: https://documentation.wazuh.com/current/installation-guide/index.html
