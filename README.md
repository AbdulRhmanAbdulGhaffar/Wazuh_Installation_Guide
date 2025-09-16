# Wazuh Installation Guide

## 📌 Description
This repository provides a **step-by-step guide** to install **Wazuh** on Ubuntu using VirtualBox or VMware. It covers environment setup, installation, and accessing the Wazuh dashboard.

---

## ⚙️ Requirements
- VirtualBox 👉 [Download here](https://www.virtualbox.org/)
- Ubuntu ISO 👉 [Ubuntu 20.04.6 LTS](https://releases.ubuntu.com/20.04/ubuntu-20.04.6-desktop-amd64.iso)
- System resources:
  - Disk space: **40 GB**
  - RAM: **4 GB minimum**
  - CPU: **3 cores**

---

## 🖥️ Supported Operating Systems
Wazuh can be installed on:
- Amazon Linux 2, Amazon Linux 2023
- CentOS 7, 8
- Red Hat Enterprise Linux 7, 8, 9
- Ubuntu 16.04, 18.04, 20.04, 22.04, 24.04

---

## 🚀 Installation Steps

### 1️⃣ Setup Virtual Machine
- Create a VM with **40GB disk**, **4GB RAM**, and **3 CPUs**.
- Mount the Ubuntu ISO.
- Install Ubuntu normally.

📷 *Add screenshot of VM setup here*

---

### 2️⃣ Open Terminal
Run:
```bash
sudo su
sudo apt update
sudo apt install curl -y
```

📷 *Add screenshot of terminal commands here*

---

### 3️⃣ Install Wazuh (Quickstart)
Run:
```bash
sudo curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

⏳ This process takes some time. Be patient.

📷 *Add screenshot of installation progress here*

---

### 4️⃣ Get Server IP
Run:
```bash
ip a
```
OR
```bash
ifconfig
```

📷 *Add screenshot of IP command output here*

---

### 5️⃣ Access Wazuh Dashboard
- Open browser → enter your server IP
  ```
  http://192.168.1.xx
  ```
- Login with credentials shown after installation.

📷 *Add screenshot of login page here*

---

### 6️⃣ Retrieve Credentials (If Not Displayed)
Run:
```bash
sudo tar -O -xvf wazuh-install-files.tar wazuh-install-files/wazuh-passwords.txt
```

Default credentials:
- **Username:** "admin"
- **Password:** "xxxxxxxxxxxxxxxxxxxxxxxxxxxx"

[![Virtual-Box-SIEM-Machine-16-09-2025-02-31-31.png](https://i.postimg.cc/ZYjNsZC7/Virtual-Box-SIEM-Machine-16-09-2025-02-31-31.png)](https://postimg.cc/xqJqqwGM)

---

## ✅ Final Result
- Wazuh Dashboard running successfully 🎉


[![Virtual-Box-SIEM-Machine-16-09-2025-00-36-47.png](https://i.postimg.cc/dVfmHFSP/Virtual-Box-SIEM-Machine-16-09-2025-00-36-47.png)](https://postimg.cc/VJjCvx8D)

---

## 🎯 Congratulations!
You have successfully installed **Wazuh** on Ubuntu using VirtualBox/VMware.
