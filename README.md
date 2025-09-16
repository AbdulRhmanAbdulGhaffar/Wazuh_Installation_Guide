# 🚀 Wazuh Installation Guide on Ubuntu (VirtualBox/VMware)

## 📌 Description
This repository provides a **step-by-step installation guide** for setting up **Wazuh SIEM** on Ubuntu inside a Virtual Machine (VirtualBox/VMware).  
It covers **environment setup, installation commands, accessing the Wazuh dashboard, and retrieving credentials**.  

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
- Create a VM with:
  - **40GB disk**, **4GB RAM**, and **3 CPUs**.  
- Mount the Ubuntu ISO.  
- Install Ubuntu normally.  

📸 *Screenshot: Ubuntu installation*  
![VM Setup](https://i.postimg.cc/hGbvJbmy/Screenshot-2025-09-16-032928.png)

---

### 2️⃣ Update & Install Dependencies
```bash
sudo su
sudo apt update
sudo apt install curl -y
```

📸 *Screenshot: Updating Ubuntu*  
![Update Terminal](https://i.postimg.cc/cCQ0jdcD/Virtual-Box-SIEM-Machine-16-09-2025-03-35-09.png)

---

### 3️⃣ Install Wazuh (Quickstart)
```bash
sudo curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

⏳ This may take several minutes.  

📸 *Screenshot: Wazuh installation process*  
![Install Wazuh](https://i.postimg.cc/y6FK7YFj/Screenshot-2025-09-16-003344.png)

---

### 4️⃣ Get Server IP
Run:
```bash
ip a
```
or
```bash
ifconfig
```

📸 *Screenshot: Checking IP address*  
![IP Address](https://i.postimg.cc/JhDwv1rb/Virtual-Box-SIEM-Machine-16-09-2025-02-31-51.png)

---

### 5️⃣ Access Wazuh Dashboard
- Open your browser → enter your server IP:
  ```
  https://<your-server-ip>
  ```
- Example:  
  ```
  https://192.168.1.xx
  ```

📸 *Screenshot: Accessing dashboard*  
![Dashboard Access](https://i.postimg.cc/3rZqLyXs/Virtual-Box-SIEM-Machine-16-09-2025-02-29-43.png)

---

### ⚠️ First-Time Browser Warning
When you first access the Wazuh dashboard, your browser will show a **security warning** (due to a self-signed SSL certificate).  

👉 To continue:  
1. Click **Advanced...**  
2. Click **Accept the Risk and Continue**  

📸 *Screenshot: Browser warning*  
![Browser Warning](https://i.postimg.cc/02bLbkSh/Virtual-Box-SIEM-Machine-16-09-2025-02-30-05.png)

---

### 🔑 Wazuh Login Page
After bypassing the security warning, you will be redirected to the **Wazuh login page**.  

Credentials:  
- **Username:** `admin`  
- **Password:** retrieved after installation or from `wazuh-passwords.txt`.  

📸 *Screenshot: Login page*  
![Login Page](https://i.postimg.cc/KzshHRLr/Virtual-Box-SIEM-Machine-16-09-2025-00-34-43.png)

---

### 6️⃣ Retrieve Credentials (If Needed)
If the password is not shown after installation, run:
```bash
sudo tar -O -xvf wazuh-install-files.tar wazuh-install-files/wazuh-passwords.txt
```

Default output:  
- **Username:** `admin`  
- **Password:** `xxxxxxxxxxxxxxxxxxxxxxxxxxxx`

📸 *Screenshot: Retrieving credentials*  
![Credentials](https://i.postimg.cc/PfYPwHkV/Virtual-Box-SIEM-Machine-16-09-2025-02-31-31.png)

---

## ✅ Final Result
If everything is correct, you should now see the **Wazuh Dashboard** 🎉  

📸 *Screenshot: Final dashboard*  
![Final Dashboard](https://i.postimg.cc/dVfmHFSP/Virtual-Box-SIEM-Machine-16-09-2025-00-36-47.png)

---

## 🛠️ Notes & Troubleshooting
- If VirtualBox screen doesn’t fit:  
  ```bash
  sudo apt install build-essential dkms linux-headers-$(uname -r) -y
  ```
- If browser shows a blank page → ensure firewall/ports are open.  
- Always copy/save the `wazuh-passwords.txt` file after installation.  

---

## 🎯 Congratulations!
You have successfully installed **Wazuh SIEM** on Ubuntu VM.  
Now you can start exploring its features for **monitoring, threat detection, and security analysis** 🚀  
