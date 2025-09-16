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

[![Screenshot-2025-09-16-032928.png](https://i.postimg.cc/hGbvJbmy/Screenshot-2025-09-16-032928.png)](https://postimg.cc/f3yDpdBm)

---

### 2️⃣ Open Terminal
Run:
```bash
sudo su
sudo apt update
sudo apt install curl -y
```

[![Virtual-Box-SIEM-Machine-16-09-2025-03-35-09.png](https://i.postimg.cc/cCQ0jdcD/Virtual-Box-SIEM-Machine-16-09-2025-03-35-09.png)](https://postimg.cc/XB7RBSmF)
---

### 3️⃣ Install Wazuh (Quickstart)
Run:
```bash
sudo curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

⏳ This process takes some time. Be patient.

[![Screenshot-2025-09-16-003344.png](https://i.postimg.cc/y6FK7YFj/Screenshot-2025-09-16-003344.png)](https://postimg.cc/YjqZ37DL)
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

[![Virtual-Box-SIEM-Machine-16-09-2025-02-31-51.png](https://i.postimg.cc/JhDwv1rb/Virtual-Box-SIEM-Machine-16-09-2025-02-31-51.png)](https://postimg.cc/hJB37R7j)
---

### 5️⃣ Access Wazuh Dashboard
- Open browser → enter your server IP
  ```
  http://192.168.1.xx
  ```
- Login with credentials shown after installation.

[![Virtual-Box-SIEM-Machine-16-09-2025-02-29-43.png](https://i.postimg.cc/3rZqLyXs/Virtual-Box-SIEM-Machine-16-09-2025-02-29-43.png)](https://postimg.cc/z3VpvGP7)
---

### ⚠️ First-Time Browser Warning  

When you first access the Wazuh dashboard using your server IP, your browser will show a **security warning**.  
This is because Wazuh uses a **self-signed SSL certificate** by default.  

To continue:  

1. Click **Advanced...**  
2. Then click **Accept the Risk and Continue** (or **Proceed to <your-ip>**)  

[![Virtual-Box-SIEM-Machine-16-09-2025-02-30-05.png](https://i.postimg.cc/02bLbkSh/Virtual-Box-SIEM-Machine-16-09-2025-02-30-05.png)](https://postimg.cc/vcwPKd3v)  
---
### 🔑 Wazuh Login Page  

After accepting the browser security warning, you will be redirected to the **Wazuh login page**.  

Here you need to enter your credentials:  

- **Username:** `admin`  
- **Password:** shown during installation (or retrieved from the `wazuh-passwords.txt` file).  

[![Virtual-Box-SIEM-Machine-16-09-2025-00-34-43.png](https://i.postimg.cc/KzshHRLr/Virtual-Box-SIEM-Machine-16-09-2025-00-34-43.png)](https://postimg.cc/dkdf7Q5L) 

---
### 6️⃣ Retrieve Credentials (If Not Displayed)
Run:
```bash
sudo tar -O -xvf wazuh-install-files.tar wazuh-install-files/wazuh-passwords.txt
```

Default credentials:
- **Username:** "admin"
- **Password:** "xxxxxxxxxxxxxxxxxxxxxxxxxxxx"

[![Virtual-Box-SIEM-Machine-16-09-2025-02-31-31.png](https://i.postimg.cc/PfYPwHkV/Virtual-Box-SIEM-Machine-16-09-2025-02-31-31.png)](https://postimg.cc/bdYz7Kr1)---

## ✅ Final Result
- Wazuh Dashboard running successfully 🎉


[![Virtual-Box-SIEM-Machine-16-09-2025-00-36-47.png](https://i.postimg.cc/dVfmHFSP/Virtual-Box-SIEM-Machine-16-09-2025-00-36-47.png)](https://postimg.cc/VJjCvx8D)

---

## 🎯 Congratulations!
You have successfully installed **Wazuh** on Ubuntu using VirtualBox/VMware.
