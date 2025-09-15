
# 🚀 تثبيت Wazuh على Ubuntu

هذا الدليل يشرح خطوة بخطوة كيفية تثبيت Wazuh على نظام Ubuntu داخل VirtualBox أو VMware.  
هيكون معاه صور توضيحية (أضف لقطات شاشة في الأماكن المحددة).  

---

## 1️⃣ المتطلبات الأساسية

قبل ما تبدأ لازم تتأكد إنك على نظام تشغيل مدعوم:  

- Amazon Linux 2, 2023  
- CentOS 7, 8  
- Red Hat Enterprise Linux 7, 8, 9  
- Ubuntu 16.04, 18.04, 20.04, 22.04, 24.04  

⚡ النسخة المستخدمة:  
[Ubuntu 20.04.6 Desktop](https://releases.ubuntu.com/20.04/ubuntu-20.04.6-desktop-amd64.iso)  

📥 لتحميل VirtualBox: [VirtualBox Official Site](https://www.virtualbox.org/)  

📸 *لقطة شاشة: شاشة تحميل Ubuntu*  

---

## 2️⃣ إعداد الجهاز الافتراضي (VM)

- مساحة القرص: **40GB**  
- الذاكرة (RAM): **4GB** على الأقل  
- عدد المعالجات (CPU): **3** أو أكثر  

📸 *لقطة شاشة: إعدادات VirtualBox أو VMware*  

---

## 3️⃣ تحديث النظام

بعد ما Ubuntu يفتح، افتح **Terminal** واكتب:  

```bash
sudo su
sudo apt update
sudo apt install curl -y
```

📸 *لقطة شاشة: أوامر التحديث في الـ Terminal*  

---

## 4️⃣ تثبيت Wazuh (Quickstart)

نزّل وشغّل أداة التثبيت:  

```bash
sudo curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

⚠️ العملية هتاخد وقت، متقلقش.  

📸 *لقطة شاشة: أثناء تثبيت Wazuh*  

---

## 5️⃣ معرفة عنوان السيرفر (IP Address)

```bash
ip a
```

أو:  

```bash
ifconfig
```

📸 *لقطة شاشة: نتيجة أمر ip a*  

---

## 6️⃣ الدخول على واجهة Wazuh

افتح المتصفح واكتب:  

```
http://<your-server-ip>
```

مثال:  
```
http://192.168.1.20
```

📸 *لقطة شاشة: صفحة تسجيل الدخول*  

- **Username**: admin  
- **Password**: بيظهر أثناء التثبيت  

لو نسيته:  

```bash
sudo tar -O -xvf wazuh-install-files.tar wazuh-install-files/wazuh-passwords.txt
```

📸 *لقطة شاشة: ملف كلمات المرور (Username + Password)*  

---

## 7️⃣ 🎉 مبروك

كده Wazuh شغال عندك، تقدر تبدأ تستخدم لوحة التحكم وتحلل الأحداث.  

📸 *لقطة شاشة: واجهة Wazuh بعد تسجيل الدخول*  
📸 *لقطة شاشة نهائية لنجاح التثبيت*  

---

## 📌 ملاحظات

- يفضل يكون الجهاز متصل بالإنترنت طول التثبيت.  
- لو حصلت أي مشكلة في الخطوات، راجع اللوجات أو جرّب إعادة التثبيت.  

---

✍️ **أعدّ بواسطة**: [اسمك هنا]  
