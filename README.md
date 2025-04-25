# DVWA (Damn Vulnerable Web Application) Penetration Testing

## Overview

This repository contains the **Damn Vulnerable Web Application (DVWA)**, a PHP/MySQL web application designed for security professionals and enthusiasts to practice web application security. The DVWA is intentionally vulnerable, allowing users to practice various penetration testing techniques in a safe and legal environment.

In this repository, the primary focus is on SQL Injection (SQLi) and performing common penetration testing activities on vulnerable web applications. This guide walks you through setting up the DVWA environment, performing penetration testing using SQL injection, and understanding the vulnerabilities within the application.

---

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
- [Penetration Testing with SQL Injection](#penetration-testing-with-sql-injection)
- [How to Use](#how-to-use)
- [Code Snippets](#code-snippets)
- [Contributing](#contributing)
- [License](#license)

---

## Introduction

The **Damn Vulnerable Web Application (DVWA)** is an intentionally vulnerable web application that allows security professionals and penetration testers to practice their skills. It includes several vulnerabilities such as SQL Injection, Cross-Site Scripting (XSS), Cross-Site Request Forgery (CSRF), and more.

This project primarily demonstrates **SQL Injection** (SQLi), where the goal is to exploit vulnerabilities in web applications to execute arbitrary SQL queries against a database.

---

## Prerequisites

Before you begin, ensure you have the following installed:

- **Linux-based environment** (Kali Linux or other)
- **Apache Web Server**
- **MariaDB/MySQL**
- **PHP** (version 7.0 or higher)
- **Git** (for version control)

---

## Setup Instructions

1. **Install Apache2, MySQL, PHP, and PHP-Mysqli**

   Open a terminal window and run the following commands to install the required software:

   ```bash
   sudo apt update
   sudo apt install apache2 mariadb-server php php-mysqli libapache2-mod-php
 
