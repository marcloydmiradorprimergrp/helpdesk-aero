# OSTicket Local Setup Guide

This guide provides instructions for setting up OSTicket locally and preparing for custom code overrides.

## Prerequisites
- PHP 7.2 or higher
- MySQL 5.5 or higher
- Web server (Apache/Nginx)
- Git (optional, for version control)

## Local Installation Steps

1. **Download OSTicket**
   - Visit [https://osticket.com/download](https://osticket.com/download)
   - Download the latest stable release
   - Extract the zip file to your web server directory (e.g., `/var/www/osticket`)

2. **Set Up Database**
   - Create a new MySQL database (e.g., `osticket_db`)
   - Create a user with full privileges for this database
   - Note down the database name, username, and password

3. **Configure Web Server**
   - For Apache:
     - Ensure `mod_rewrite` is enabled
     - Set document root to the OSTicket folder
   - For Nginx:
     - Configure server block to point to OSTicket directory
     - Add rewrite rules if needed

4. **Run Installation Wizard**
   - Open browser and navigate to `http://localhost/osticket/setup`
   - Follow the installation wizard:
     - Enter database credentials
     - Set admin username and password
     - Complete installation

5. **Post-Installation**
   - Remove or rename the `setup` directory
   - Set proper permissions:
     ```bash
     chmod 0644 include/ost-config.php
     chown www-data:www-data include/ost-config.php
