# Ansible Playbooks Overview

This repository contains various Ansible playbooks for different tasks including service configuration, package installation, and user management. Below is an overview of each playbook.

## 1. Enable Service on Firewalld

This playbook configures the firewall to open a port and ensures that the `firewalld` service is running and reloaded when changes are made.

- **File Name:** `enable_firewalld_service.yml`
- **Purpose:** Configures the firewall to allow HTTP traffic and ensures `firewalld` is running and reloaded.
- **Key Tasks:**
  - Open port 80 for HTTP traffic.
  - Ensure the `firewalld` service is started.
  - Reload the `firewalld` service to apply changes.

### 2. Install Apache WebServer

This playbook installs the Apache HTTP server based on the operating system type.

- **File Name:** `install_apache.yml`
- **Purpose:** Installs Apache HTTP server on Ubuntu or CentOS based on the OS family.
- **Key Tasks:**
  - Install Apache (`apache2`) on Ubuntu.
  - Install Apache (`httpd`) on CentOS.

### 3. Install Packages Through Loop

This playbook installs a list of packages using a loop.

- **File Name:** `install_packages_loop.yml`
- **Purpose:** Installs a list of packages specified in a variable.
- **Key Tasks:**
  - Install packages using `yum` with a loop.

### 4. Create Users Through Loop

This playbook creates a list of users using a loop.

- **File Name:** `create_users_loop.yml`
- **Purpose:** Creates users specified in a variable.
- **Key Tasks:**
  - Create users using the `user` module with a loop.

### 5. Verify Apache Installation

This playbook ensures Apache is up-to-date, copies an updated configuration file, and ensures the service is running.

- **File Name:** `verify_apache_installation.yml`
- **Purpose:** Verifies Apache installation, updates the configuration, and restarts the service if necessary.
- **Key Tasks:**
  - Ensure Apache is at the latest version.
  - Copy an updated Apache configuration file.
  - Ensure Apache is running.
  - Restart Apache if configuration changes.
