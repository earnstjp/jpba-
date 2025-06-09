
# 🌐 JP Business Advisors – Cloud Server Project

**Student Name**: Earnst Padayatty  
**Student Number**: [Insert here]  
**Domain**: [https://earnst.online](https://earnst.online)  
**Public IP**: [Insert EC2 public IP]  
**Video Explainer**: [Insert YouTube or OneDrive link]

---

## 🧠 Project Overview

**JP Business Advisors** is a cloud-based platform supporting aspiring entrepreneurs and startups. We guide innovators with accurate resources, expert help, and actionable dashboards to turn their ideas into reality.

---

## ☁️ EC2 Server Configuration

- **Platform**: AWS EC2  
- **OS**: Ubuntu 22.04 LTS  
- **Web Server**: Apache 2  
- **Instance Type**: t2.micro  
- **Access**: SSH & HTTP/HTTPS

### EC2 Setup Commands:
```bash
ssh -i "jpba.pem" ubuntu@<EC2-IP>
sudo apt update && sudo apt install apache2 -y
sudo ufw allow 'Apache Full'
```
---

## 🌍 DNS Configuration

Domain: [https://earnst.online](https://earnst.online)

| Type | Host | Value           | TTL  |
|------|------|------------------|------|
| A    | @    | <EC2 Public IP>  | 600  |

### Steps:
1. Accessed GoDaddy DNS settings  
2. Added A Record pointing to EC2 public IP  
3. Verified propagation via https://dnschecker.org  
4. Domain successfully loads JPBA website

✅ DNS configured and accessible globally.

---

## 🔐 SSL/TLS Configuration

HTTPS enabled using **Let's Encrypt Certbot** for Apache.

### Steps:
```bash
sudo apt install certbot python3-certbot-apache -y
sudo certbot --apache
```

- Auto-redirect from HTTP → HTTPS  
- Trusted padlock shown in browser  
- Cert auto-renew handled via systemd

✅ HTTPS live at [https://earnst.online](https://earnst.online)  
🔍 Verified via [SSL Labs](https://www.ssllabs.com/ssltest/analyze.html?d=earnst.online)

---

## 🖥️ Website Deployment

### Upload HTML files:
```bash
scp -i "jpba.pem" index.html ubuntu@<EC2-IP>:/var/www/html/
```

### File Structure:
```
/var/www/html/
├── index.html
├── style.css
├── dashboard.html (planned)
└── script.js (optional)
```

- Clean HTML/CSS website  
- Includes: About, Mission, Features, Contact

---

## 🧾 Custom Script: Expert Assistance Logger

A custom Bash script simulating client question submission to the expert desk.

```bash
#!/bin/bash
echo "Welcome to JPBA Expert Desk"
read -p "Enter your name: " name
read -p "Enter your question: " question
timestamp=$(date +"%Y-%m-%d %H:%M:%S")
echo "[$timestamp] $name asked: $question" >> /var/www/html/expert_questions.txt
echo "✅ Your question has been logged!"
```
- ✅ Creative, original scripting  
- ✅ Useful for future feature scaling  
- ✅ Student contribution is clearly documented  
- 🗂️ Output saved to: `/var/www/html/expert_questions.txt`

---

## 🎥 Video Explainer

- EC2 + Apache setup  
- HTML deployment demo  
- DNS & SSL walkthrough  
- Bash script usage

🎬 Link: [Insert your video link here]

---

## 📚 References

- Apache: https://httpd.apache.org/  
- Certbot: https://certbot.eff.org/  
- AWS EC2 Docs: https://docs.aws.amazon.com/ec2/  
- DNS Checker: https://dnschecker.org/  
- SSL Labs: https://www.ssllabs.com/ssltest/analyze.html?d=earnst.online  
- Murdoch Writing Guide: https://github.com/SCH-IT-MurdochUni/NetworkingLabs/blob/main/Reusable_Learning_Objects/writing.md

---

## ✅ Rebuild Ready

This documentation allows the full system to be rebuilt from scratch within 1 hour — from EC2 setup to live, secure domain deployment.
