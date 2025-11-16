# **Install the Wazuh Agent on an Ubuntu Client**

### **Prerequisites**

- A functional Wazuh server setup.
- Access to the Ubuntu client machine where the agent will be installed.
- Administrator or root privileges on both the server and client machine.

# **Steps to Install the Wazuh Agent**

### **Step 1: Access the Wazuh Dashboard**

Open your Wazuh dashboard in the browser. Navigate to the home screen to confirm that there are no active agents and note any disconnected agents.

![](https://thecyberreactor.in/wp-content/uploads/2024/12/image-4.png)

### **Step 2: Navigate to Server Management**

Click the options menu, go to **Server Management**, and then click on **Endpoints Summary**.

![](https://thecyberreactor.in/wp-content/uploads/2024/12/image-5.png)

### **Step 3: Deploy a New Agent**

On the dashboard, select **Deploy New Agent**.

![](https://thecyberreactor.in/wp-content/uploads/2024/12/image-6.png)

### **Step 4: Choose the Operating System**

Select the operating system for your client machine. In this case, choose Ubuntu.

### **Step 5: Assign the Server Address**

Input your server’s address:

- If your Wazuh server is installed on the same machine, use the IP address in your URL.
- If the server is hosted on a different machine, provide that machine’s IP address.

### **Step 6: Set an Agent Name**

Assign a unique name for the agent. Ensure it’s easily identifiable within your environment.

![](https://thecyberreactor.in/wp-content/uploads/2024/12/image-7.png)

### **Step 7: Select a Group**

Choose a group for the agent. By default, select “default.”

### **Step 8: Copy the Installation Command**

A command will be generated to download and install the agent. Copy this command.

![](https://thecyberreactor.in/wp-content/uploads/2024/12/image-8.png)

### **Step 9: Install the Agent on the Client Machine**

On your Ubuntu client machine, open the terminal, paste the copied command, and press **Enter**. Wait for the installation process to complete.

![](https://thecyberreactor.in/wp-content/uploads/2024/12/image-9.png)

### **Step 10: Start and Enable the Wazuh Agent**

Run the following commands in the terminal to start and enable the Wazuh agent:

```
sudo systemctl enable wazuh-agent
sudo systemctl start wazuh-agent
sudo systemctl status wazuh-agent
```

![](https://thecyberreactor.in/wp-content/uploads/2024/12/image-10.png)

Once done, return to your Wazuh dashboard and confirm that the new agent is active.
