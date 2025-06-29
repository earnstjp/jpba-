
# JP Business Advisors – Cloud-Server Project

**Student Name**: Earnst Padayatty  

**Student Number**: 35559321 

**Domain**: [earnst.online](https://earnst.online) 

**Public IP**: [3.107.125.181](http://3.107.125.181)

**Video Explainer**: [https://drive.google.com/file/d/1HuXC15eu8KlxFbHX4SIONvmkWGEdCRHF/view?usp=drivesdk]

---

## Project Overview

**JP Business Advisors** is a cloud-based platform supporting aspiring entrepreneurs and startups. We guide innovators with accurate resources, expert help, and actionable dashboards to turn their ideas into reality.This documentatin will allow any user to build a server from scratch within short span of time. This project is all about launching an instance through a Iaas platform and linking it to domain and engaging with the process involved.


---
---

## Process involved

STEP 1: Launch EC2 Instance

AMI: Choose Amazon Linux 2 or Ubuntu.

Instance type: t2.micro (Free Tier eligible).

Create or choose an existing .pem key pair.

Security Group:

Allow HTTP and SSH from your IP or anywhere.

Click Launch Instance.

STEP 2: Connect to Your EC2

Copy the Public IP address.

Use following commands in the process :
chmod 400 earnst6
ssh -i earnst6 ec2-user@<http://3.107.125.181/>


STEP 3: Link Domain (e.g. from GoDaddy)

Go to your domain provider 

Find DNS Management for your domain.

Edit or Add an A Record.

STEP 4 : Secure your web server through lets certbot command.

---
##  EC2 Server Configuration

- **Platform**: AWS EC2  
- **OS**: Ubuntu   
- **Web Server**: Apache 2  
- **Instance Type**: t2.micro  
- **Access**: SSH & HTTP/HTTPS

### EC2 Setup Commands:
```bash
ssh -i "earnst06" ubuntu@<3.107.125.181>
sudo apt update && sudo apt install apache2 -y
sudo ufw allow 'Apache Full'
```
---

## DNS Configuration

Domain: [https://earnst.online](https://earnst.online)

| Type | Host | Value           | TTL  |
|------|------|------------------|------|
| A    | @    | <3.107.125.181>  | 600  |

### Steps:
1. Accessed GoDaddy DNS settings  
2. Added A Record pointing to EC2 public IP  
3. Verified propagation   
4. Domain successfully loads the website

 DNS configured and accessible globally.

---

## SSL/TLS Configuration

HTTPS enabled using **Let's Encrypt Certbot** for Apache.

### Steps:
```bash
sudo apt install certbot python3-certbot-apache -y
sudo certbot --apache
```

- Auto-redirect from HTTP to HTTPS  
- Website secured. 
- Cert auto-renew handled via systemd
- Certificate obtained successfully
 HTTPS live at [https://earnst.online](https://earnst.online)  
   Verified via [SSL Labs](https://www.ssllabs.com/ssltest/analyze.html?d=earnst.online)

---

##  Website Deployment

### HTML:
```bash
scp -i "earnst06" index.html ubuntu@<3.107.125.181>:/var/www/html/
```

### File Structure:
```
/var/www/html/
├── index.html
├── style.css
├── dashboard.html 
└── script.js 
```

- Clean HTML,JS,CSS website  
- Includes: About, Mission, Features, Contact

---



##  Video Explainer

- EC2 AWS walkthrough 
- HTML deployment demo  
- DNS & SSL walkthrough  
- Bash script usage

🎬 Link:https://drive.google.com/file/d/1HuXC15eu8KlxFbHX4SIONvmkWGEdCRHF/view?usp=drivesdk


---

##  Conclusion

This documentation allows the full system to be rebuilt from scratch instantly through Amazon EC2.
