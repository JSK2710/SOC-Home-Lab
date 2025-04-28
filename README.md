# 🛡️ SOC Home Lab: Wazuh Server and Agent Installation on Ubuntu

This project outlines the setup of a home-based Security Operations Center (SOC) using Wazuh, an open-source security monitoring platform. The lab environment includes the installation and configuration of both the Wazuh server and agent on Ubuntu systems, facilitating real-time security event monitoring and analysis.

## 📌 Project Overview

- **Objective:** Establish a functional SOC environment by deploying Wazuh server and agent on Ubuntu machines.
- **Components:**
  - **Wazuh Server:** Centralized platform for collecting, analyzing, and visualizing security data.
  - **Wazuh Agent:** Installed on client machines to monitor and send security events to the server.

## 🧰 Tools and Technologies

- **Operating System:** Ubuntu Linux
- **Security Platform:** [Wazuh](https://wazuh.com/)
- **Installation Guides:**
  - [How to Install Wazuh on Ubuntu](https://thecyberreactor.in/how-to-install-wazuh-on-ubuntu/)
  - [How to Install the Wazuh Agent on an Ubuntu Client](https://thecyberreactor.in/how-to-install-the-wazuh-agent-on-an-ubuntu-client/)

## 🛠️ Installation Steps

### 1. Wazuh Server Installation

Follow the detailed guide provided by The Cyber Reactor to install the Wazuh server components:

- **Guide:** [How to Install Wazuh on Ubuntu](https://thecyberreactor.in/how-to-install-wazuh-on-ubuntu/)

Key steps include:

- Updating the system packages.
- Downloading and executing the Wazuh installation assistant script.
- Starting Wazuh services: indexer, manager, and dashboard.
- Accessing the Wazuh web interface via the server's IP address.

### 2. Wazuh Agent Installation on Ubuntu Client

Install the Wazuh agent on a separate Ubuntu client machine to enable event monitoring:

- **Guide:** [How to Install the Wazuh Agent on an Ubuntu Client](https://thecyberreactor.in/how-to-install-the-wazuh-agent-on-an-ubuntu-client/)

Key steps include:

- Downloading and installing the Wazuh agent package.
- Configuring the agent to communicate with the Wazuh server.
- Starting the Wazuh agent service.
- Verifying agent registration on the Wazuh dashboard.

## 📊 Dashboard Access

After successful installation:

- Access the Wazuh dashboard by navigating to `https://<wazuh-server-ip>` in your web browser.
- Use the credentials provided during the installation to log in.
- Monitor connected agents and analyze security events in real-time.


## 🎯 Outcomes and Skills Acquired

- **SIEM Deployment:** Gained hands-on experience in deploying a Security Information and Event Management system.
- **Agent Management:** Learned to install and configure agents for data collection.
- **Security Monitoring:** Developed skills in monitoring and analyzing security events through the Wazuh dashboard.

## 📚 References

- [Wazuh Official Documentation](https://documentation.wazuh.com/current/index.html)
- [The Cyber Reactor Blog](https://thecyberreactor.in/)

---

*This project serves as a foundational step towards building a comprehensive SOC environment for cybersecurity monitoring and analysis.*



