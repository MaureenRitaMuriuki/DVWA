# DVWA (Damn Vulnerable Web Application) Penetration Testing Setup

This repository provides instructions on setting up **DVWA (Damn Vulnerable Web Application)** for penetration testing practice. DVWA is a PHP/MySQL web application that is deliberately vulnerable to a range of security issues, allowing users to test and improve their security skills.

The following instructions detail the entire process from **Step 2** onward, including system setup, installation, and database configuration.

---

## Prerequisites

Make sure the following are installed on your machine:

1. **Linux-based environment (preferably Kali Linux)**.
2. **Apache Web Server** (for serving the web pages).
3. **MariaDB/MySQL** (to store and retrieve data).
4. **PHP 7.0+** (for running PHP scripts in DVWA).
5. **Git** (to clone the repository).

---

## Step 1: Install Apache, MySQL, PHP, and PHP-Mysqli

```bash
sudo apt update
sudo apt install apache2 mariadb-server php php-mysqli libapache2-mod-php
--
## Step 2: Clone DVWA Repository

1. Navigate to the `/var/www/html/` directory on your system:

   ```bash
   cd /var/www/html/
Clone the DVWA repository from GitHub:

bash
Copy
Edit
git clone https://github.com/digininja/DVWA.git
This will download the DVWA folder to /var/www/html/.

Step 3: Set Up the Database
Now, set up the database for DVWA:

Log into MySQL/MariaDB as the root user:

bash
Copy
Edit
mysql -u root -p
Create the dvwa database:

sql
Copy
Edit
CREATE DATABASE dvwa;
Create the dvwa user and grant privileges:

sql
Copy
Edit
GRANT ALL PRIVILEGES ON dvwa.* TO 'dvwa'@'localhost' IDENTIFIED BY 'yourpassword';
FLUSH PRIVILEGES;
Replace 'yourpassword' with the password you want to assign to the dvwa user.

Step 4: Configure DVWA to Connect to the Database
Navigate to the config folder in the DVWA directory:

bash
Copy
Edit
cd /var/www/html/DVWA/config
Open the config.inc.php file for editing:

bash
Copy
Edit
sudo nano config.inc.php
Modify the database settings to reflect your local setup:

php
Copy
Edit
$_DVWA['db_server']   = '127.0.0.1';    // Database server
$_DVWA['db_database'] = 'dvwa';         // Database name
$_DVWA['db_user']     = 'dvwa';         // Database username
$_DVWA['db_password'] = 'yourpassword'; // Database password
Replace 'yourpassword' with the password you set for the dvwa user.

Save and exit by pressing CTRL + O, then Enter, and then CTRL + X.

Step 5: Finalize DVWA Setup
Now, complete the setup process by initializing the database:

Open your browser and navigate to:

bash
Copy
Edit
http://localhost/DVWA/setup.php
Click Create/Reset Database to create the necessary tables in the database.

Step 6: Set Permissions for DVWA Directory
Ensure the correct permissions are set for the DVWA directory:

bash
Copy
Edit
sudo chown -R www-data:www-data /var/www/html/DVWA
This ensures that the Apache web server (www-data user) can access the files.

Step 7: Access DVWA in Your Browser
Open your browser and navigate to:

bash
Copy
Edit
http://localhost/DVWA
Login with the default credentials:

Username: admin

Password: password

You can now begin testing DVWA's vulnerabilities like SQL Injection, Cross-Site Scripting (XSS), and other security issues.

Step 8: Enable DVWA Security Levels
After logging in to DVWA, you can change the security level to practice different penetration testing techniques:

Click on DVWA Security in the navigation menu.

Set the security level to Low, Medium, or High depending on the difficulty level you want to test.

Conclusion
You have successfully set up the DVWA (Damn Vulnerable Web Application) for penetration testing practice. You can now use this application to explore vulnerabilities, test exploitation techniques, and improve your security skills.

Happy testing!

yaml
Copy
Edit

---

### How to use this:

1. Copy the content above.
2. Create a new file named `README.md` in your project folder (e.g., `/var/www/html/DVWA`).
3. Paste the content into `README.md`.
4. Save the file.

This will give you a clear, step-by-step guide to setting up DVWA from **Step 2** onward.







