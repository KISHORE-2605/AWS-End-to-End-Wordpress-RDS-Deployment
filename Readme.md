<div align="center">

# ☁️ AWS End-to-End WordPress RDS Deployment

### Deploying a Production-Ready WordPress Website Using Amazon EC2 and Amazon RDS (MySQL)

![AWS](https://img.shields.io/badge/AWS-Cloud-orange?style=for-the-badge&logo=amazonaws)
![EC2](https://img.shields.io/badge/EC2-Web%20Server-blue?style=for-the-badge)
![RDS](https://img.shields.io/badge/Amazon-RDS-527FFF?style=for-the-badge&logo=amazonrds)
![WordPress](https://img.shields.io/badge/WordPress-CMS-21759B?style=for-the-badge&logo=wordpress)
![Linux](https://img.shields.io/badge/Linux-Amazon%20Linux-yellow?style=for-the-badge&logo=linux)
![Apache](https://img.shields.io/badge/Apache-Web%20Server-red?style=for-the-badge&logo=apache)
![PHP](https://img.shields.io/badge/PHP-Backend-777BB4?style=for-the-badge&logo=php)

</div>

---

# 📖 Project Overview

This project demonstrates how to deploy a **production-ready WordPress website** on **Amazon EC2** with **Amazon RDS (MySQL)** as the backend database.

The web server is hosted on an EC2 instance running **Apache** and **PHP**, while the database is securely managed using **Amazon RDS**. This architecture separates the application and database layers, improving scalability, security, and maintainability.

---

# 🏗️ Architecture

```
                      Internet
                          │
                    Public IP Address
                          │
                  +------------------+
                  |   Amazon EC2     |
                  | Apache + PHP     |
                  |   WordPress      |
                  +--------+---------+
                           │
                    Port 3306
                           │
                  +--------▼---------+
                  |   Amazon RDS     |
                  |     MySQL        |
                  | WordPress DB     |
                  +------------------+
```

---

# ☁️ AWS Services Used

- Amazon EC2
- Amazon RDS (MySQL)
- Amazon VPC
- Security Groups
- Internet Gateway
- Amazon Linux 2023
- Apache HTTP Server (httpd)
- PHP
- MariaDB Client
- WordPress

---

# 🚀 Features

- WordPress Hosted on Amazon EC2
- Amazon RDS as Backend Database
- Apache Web Server
- PHP Integration
- Secure Database Connectivity
- Production-Style Cloud Architecture
- Scalable Deployment
- Linux Administration

---

# 🛠️ Implementation Steps

## Step 1 – Launch an EC2 Instance

- Amazon Linux 2023
- Allow SSH (22)
- Allow HTTP (80)

---

## Step 2 – Install Apache

```bash
sudo dnf install httpd -y
sudo systemctl enable httpd
sudo systemctl start httpd
```

---

## Step 3 – Install PHP

```bash
sudo dnf install php php-mysqlnd -y
```

---

## Step 4 – Download and Configure WordPress

```bash
wget https://wordpress.org/latest.tar.gz

tar -xvf latest.tar.gz

sudo cp -r wordpress/* /var/www/html/
```

---

## Step 5 – Create Amazon RDS

- Engine : MySQL
- Username : admin
- Port : 3306

---

## Step 6 – Install MariaDB Client

```bash
sudo dnf install mariadb105 -y
```

---

## Step 7 – Connect EC2 to Amazon RDS

```bash
mysql -h <RDS-ENDPOINT> -P 3306 -u admin -p
```

---

## Step 8 – Create WordPress Database

```sql
CREATE DATABASE wordpress;

SHOW DATABASES;
```

---

## Step 9 – Configure WordPress

Edit the configuration file:

```bash
sudo cp wp-config-sample.php wp-config.php
sudo vi wp-config.php
```

Update the following database details:

```php
DB_NAME     = wordpress
DB_USER     = admin
DB_PASSWORD = YourPassword
DB_HOST     = RDS-ENDPOINT
```

---

## Step 10 – Complete WordPress Installation

Open your browser and visit:

```
http://<EC2-Public-IP>
```

Complete the WordPress setup wizard.

---

## 💻 MariaDB Client Installation

<img src="./images/mariadb-client-installation.png" width="900">

---

## 🔗 EC2 Connected to Amazon RDS

<img src="./images/ec2-rds-database-connection.png" width="900">

---

## 🗄️ Amazon RDS MySQL Creation

<img src="./images/amazon-rds-mysql-creation.png" width="900">

---

## ⚙️ WordPress Admin Dashboard

<img src="./images/wordpress-admin-dashboard.png" width="900">

---

## 🌐 WordPress Home Page

<img src="./images/wordpress-homepage.png" width="900">
---

# 📁 Project Structure

```
AWS-End-to-End-WordPress-RDS-Deployment/
│
├── README.md
│
├── images/
│   ├── ec2-instance.png
│   ├── rds-instance.png
│   ├── mysql-connection.png
│   ├── database-created.png
│   ├── wordpress-installation.png
│   └── wordpress-home.png
│
└── commands.md
```

---

# 🎯 Skills Demonstrated

- Amazon EC2
- Amazon RDS (MySQL)
- WordPress Deployment
- Apache HTTP Server
- PHP
- MariaDB Client
- Linux Administration
- Cloud Infrastructure
- Security Groups
- VPC
- Database Connectivity

---

# 📚 Learning Outcomes

- Launched and configured Amazon EC2.
- Installed Apache, PHP, and WordPress.
- Created and configured Amazon RDS (MySQL).
- Connected EC2 to RDS using MariaDB Client.
- Configured WordPress with an external database.
- Deployed a production-style cloud application.
- Gained hands-on experience with AWS compute, storage, networking, and database services.

---

# 👨‍💻 Author

**Kishore G**

**Aspiring AWS Cloud & DevOps Engineer**

- GitHub: https://github.com/KISHORE-2605
- LinkedIn: https://www.linkedin.com/in/kishore-g005
