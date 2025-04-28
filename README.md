# 🛡️ DVWA (Damn Vulnerable Web Application) Penetration Testing Setup

This repository provides instructions on setting up **DVWA (Damn Vulnerable Web Application)** for penetration testing practice.  
DVWA is a PHP/MySQL web application that is deliberately vulnerable to a range of security issues, allowing users to test and improve their security skills.

The following instructions detail the entire process from system setup, installation, and database configuration.

---

## 📋 Prerequisites

Make sure the following are installed on your machine:

1. **Linux-based environment (preferably Kali Linux)**.
2. **Apache Web Server** (for serving the web pages).
3. **MariaDB/MySQL** (to store and retrieve data).
4. **PHP 7.0+** (for running PHP scripts in DVWA).
5. **Git** (to clone the repository).

---

## 🛠️ Step 1: Install Apache, MySQL, PHP, and PHP-Mysqli

```bash
sudo apt update
sudo apt install apache2 mariadb-server php php-mysqli libapache2-mod-php
```

---

## 🛠️ Step 2: Clone DVWA Repository

1. Navigate to the `/var/www/html/` directory:

```bash
cd /var/www/html/
```

2. Clone the DVWA repository from GitHub:

```bash
git clone https://github.com/digininja/DVWA.git
```

This will download the DVWA folder into `/var/www/html/`.

---

## 🛠️ Step 3: Set Up the Database

1. Log into MySQL/MariaDB as the root user:

```bash
mysql -u root -p
```

2. Create the DVWA database:

```sql
CREATE DATABASE dvwa;
```

3. Create a new user and grant privileges:

```sql
GRANT ALL PRIVILEGES ON dvwa.* TO 'dvwa'@'localhost' IDENTIFIED BY 'yourpassword';
FLUSH PRIVILEGES;
EXIT;
```

> 🔔 Replace **'yourpassword'** with a secure password you choose.

---

## 🛠️ Step 4: Configure DVWA to Connect to the Database

1. Navigate to the config folder:

```bash
cd /var/www/html/DVWA/config
```

2. Copy the sample config file:

```bash
cp config.inc.php.dist config.inc.php
```

3. Open `config.inc.php` for editing:

```bash
sudo nano config.inc.php
```

4. Modify the database settings:

```php
$_DVWA['db_server']   = '127.0.0.1';    // Database server
$_DVWA['db_database'] = 'dvwa';         // Database name
$_DVWA['db_user']     = 'dvwa';          // Database username
$_DVWA['db_password'] = 'yourpassword'; // Database password
```

> 🔔 Again, replace **'yourpassword'** with the password you set earlier.

5. Save and exit (`CTRL + O`, `Enter`, `CTRL + X`).

---

## 🛠️ Step 5: Finalize DVWA Setup

1. Open your browser and go to:

```
http://localhost/DVWA/setup.php
```

2. Click **Create/Reset Database** to initialize DVWA.

---

## 🛠️ Step 6: Set Permissions for DVWA Directory

Ensure the Apache web server has the correct permissions:

```bash
sudo chown -R www-data:www-data /var/www/html/DVWA
```

---

## 🛠️ Step 7: Access DVWA in Your Browser

1. Open:

```
http://localhost/DVWA
```

2. Login with the default credentials:

- **Username:** admin  
- **Password:** password

You can now explore DVWA vulnerabilities like SQL Injection, XSS, Command Execution, and more.

---

## 🛠️ Step 8: Enable DVWA Security Levels

After logging into DVWA:

1. Click **DVWA Security** from the navigation menu.
2. Set the security level to:
   - **Low**
   - **Medium**
   - **High**

Depending on the difficulty you want to test.

---

## 🎯 Conclusion

You have successfully set up **DVWA (Damn Vulnerable Web Application)** for penetration testing practice.  
You can now use this environment to explore vulnerabilities, test exploitation techniques, and improve your cybersecurity skills.

Happy hacking and learning! 🚀

---







