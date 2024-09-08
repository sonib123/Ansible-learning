# Ansible Playbooks Overview

This repository contains various Ansible playbooks for different tasks including package installation, file operations, and server setup. Below is an overview of each playbook.

## Playbooks

### 1. **Install and Start HTTPD**

This playbook installs the `httpd` package and starts the `httpd` service.

- **File Name:** `install_httpd.yml`
- **Purpose:** Ensures the Apache HTTP server is installed and running.
- **Key Tasks:**
  - Install the `httpd` package.
  - Start the `httpd` service.

### 2. Install Packages

This playbook installs various packages including Apache, NTP/Chrony, and DNS.

- **File Name:** `install_packages.yml`
- **Purpose:** Installs `httpd`, `ntpd` or `chrony`, and `named` packages.
- **Key Tasks:**
  - Install the Apache package (`httpd`).
  - Install either `ntpd` or `chrony` for time synchronization.
  - Install the DNS package (`named`).

### 3. Role-Based Installation

This playbook applies different roles based on the host.

- **File Name:** `role_based_install.yml`
- **Purpose:** Uses roles for different types of installations.
- **Key Tasks:**
  - Apply the `fullinstall` role to all hosts.
  - Apply the `basicinstall` role to localhost.

### 4. Copy File to Remote Clients

This playbook copies a file from the local machine to remote clients.

- **File Name:** `copy_file.yml`
- **Purpose:** Copies a specified file to `/tmp` on all remote hosts.
- **Key Tasks:**
  - Copy a file from `/home/iafzal/somefile` to `/tmp`.
  - Set the file owner, group, and permissions.

### 5. Create a File

This playbook creates a file on the local machine.

- **File Name:** `create_file.yml`
- **Purpose:** Creates a file named `kramer.txt` in `/tmp` on the local host.
- **Key Tasks:**
  - Create a file with the name `kramer.txt` in `/tmp`.

### 6. Setup Apache Server and Configure Firewall

This playbook installs, starts the Apache server, and configures the firewall to allow HTTP traffic.

- **File Name:** `setup_apache.yml`
- **Purpose:** Sets up the Apache HTTP server and configures the firewall.
- **Key Tasks:**
  - Install the `httpd` package.
  - Start the `httpd` service.
  - Open port 80 in the firewall.
  - Reload the firewall to apply changes.

### 7. Print Hello World

This playbook demonstrates basic variable usage in Ansible.

- **File Name:** `print_hello_world.yml`
- **Purpose:** Prints a message using Ansible variables.
- **Key Tasks:**
  - Print "Hello World!" using the `debug` module.

### 8. Package Installation with Variables

This playbook demonstrates the use of variables to install and start a package.

- **File Name:** `package_installation.yml`
- **Purpose:** Installs and starts a package specified by a variable.
- **Key Tasks:**
  - Install a package specified by the `pack` variable.
  - Start the service corresponding to the package.
