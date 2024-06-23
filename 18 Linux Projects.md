# Linux Projects 🛠️

## Build a Basic Backup Script using rsync

### Objective

Create a simple backup script using `rsync` to automate the backup of files and directories from one location to another.

### Steps

1. **Install rsync (if not already installed):**
   ```bash
   sudo apt update
   sudo apt install rsync
   ```

2. **Create a backup script (`backup.sh`):**

   ```bash
   #!/bin/bash

   # Source and destination directories
   SRC="/path/to/source"
   DEST="/path/to/backup"

   # Execute rsync command for backup
   rsync -avz --delete $SRC $DEST

   # Optional: Add timestamp to log file
   echo "Backup completed on $(date)" >> /var/log/backup.log
   ```

3. **Make the script executable:**
   ```bash
   chmod +x backup.sh
   ```

4. **Schedule the backup using cron:**

   - Edit cron jobs with `crontab -e` and add:
     ```cron
     0 3 * * * /path/to/backup.sh  # Run backup script daily at 3 AM
     ```

   - Adjust the schedule (`0 3 * * *` represents every day at 3 AM) as per your requirement.

5. **Monitor the backup logs (`/var/log/backup.log`) for status and errors.**

## Set up a LAMP Stack (Linux, Apache, MySQL, PHP)

### Objective

Configure a LAMP stack on Linux for hosting dynamic websites and web applications.

### Steps

1. **Install Apache web server:**
   ```bash
   sudo apt update
   sudo apt install apache2
   ```

2. **Install MySQL database server:**
   ```bash
   sudo apt install mysql-server
   sudo mysql_secure_installation  # Secure MySQL installation
   ```

3. **Install PHP and necessary modules:**
   ```bash
   sudo apt install php libapache2-mod-php php-mysql
   ```

4. **Verify Apache and PHP installation:**
   - Create a test PHP file (`info.php`) in Apache web root:
     ```bash
     sudo nano /var/www/html/info.php
     ```
     Add:
     ```php
     <?php
     phpinfo();
     ?>
     ```

5. **Access `http://localhost/info.php` to verify PHP info page.**

## Create a Dockerized Web Application

### Objective

Containerize a web application using Docker for portability and scalability.

### Steps

1. **Install Docker on Linux:**
   - Follow Docker installation instructions from [Docker's official website](https://docs.docker.com/engine/install/).

2. **Create Dockerfile for web application:**

   ```Dockerfile
   # Use official PHP Apache image
   FROM php:apache

   # Copy application files to container
   COPY . /var/www/html

   # Expose port 80
   EXPOSE 80
   ```

3. **Build Docker image:**
   ```bash
   docker build -t my-web-app .
   ```

4. **Run Docker container:**
   ```bash
   docker run -d -p 8080:80 my-web-app
   ```

5. **Access web application at `http://localhost:8080`.**

## Implement Network Monitoring with Nagios

### Objective

Set up Nagios to monitor network services, servers, and infrastructure for proactive management and issue resolution.

### Steps

1. **Install Nagios on Linux:**
   - Follow Nagios installation instructions from [Nagios Core Documentation](https://assets.nagios.com/downloads/nagioscore/docs/nagioscore/4/en/quickstart.html).

2. **Configure Nagios for monitoring:**

   - Define hosts, services, and commands in Nagios configuration files (`/etc/nagios`).

3. **Install Nagios plugins for extending monitoring capabilities:**
   ```bash
   sudo apt install nagios-plugins
   ```

4. **Access Nagios web interface:**
   - Open `http://localhost/nagios` in a web browser.

5. **Monitor network services and infrastructure health from Nagios dashboard.**

## Automate System Updates with cron and ansible

### Objective

Automate Linux system updates using cron for scheduling and Ansible for configuration management and orchestration.

### Steps

1. **Set up cron job for automated updates:**

   - Edit cron jobs with `crontab -e` and add:
     ```cron
     0 2 * * * /usr/bin/apt update && /usr/bin/apt upgrade -y
     ```
     - This example schedules system updates daily at 2 AM.

2. **Install Ansible on Linux:**
   ```bash
   sudo apt update
   sudo apt install ansible
   ```

3. **Create Ansible playbook (`update.yml`) for system updates:**

   ```yaml
   ---
   - name: Update all packages
     hosts: all
     become: true
     tasks:
       - name: Update apt package cache
         apt:
           update_cache: yes

       - name: Upgrade all packages
         apt:
           upgrade: yes
   ```

4. **Run Ansible playbook for automated updates:**
   ```bash
   ansible-playbook update.yml
   ```

5. **Monitor and review automated update logs (`/var/log/apt/history.log`) for status and errors.**

## Summary

These Linux projects provide hands-on experience and practical skills in system administration, web hosting, containerization, monitoring, and automation. Building a backup script with rsync enhances data protection and recovery, while setting up a LAMP stack enables hosting dynamic websites and applications. Containerizing a web application with Docker offers scalability and portability advantages, and implementing network monitoring using Nagios ensures proactive management of infrastructure.

Automating system updates using cron and Ansible improves efficiency and reliability in maintaining Linux systems. These projects collectively contribute to developing comprehensive skills in Linux administration and deployment, preparing users for real-world scenarios and challenges in IT operations.

