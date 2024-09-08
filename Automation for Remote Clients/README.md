# Ansible Playbook Overview

This repository contains several Ansible playbooks for common administrative tasks, including user creation, connectivity checking, and file transfers between local and remote systems. Each playbook is designed to execute on all defined hosts (`hosts: all`), and some tasks require elevated privileges (`become: true`).

## Playbooks

### 1. **Playbook for Creating Users**

This playbook creates a user on all specified hosts.

- **File Name:** `create_user.yml`
- **Purpose:** Creates a user named `george` on all target hosts, setting up their home directory and shell configuration.
- **Key Task:**
  - Create a user with the following attributes:
    - **Username:** `george`
    - **Home Directory:** `/home/george`
    - **Shell:** `/bin/bash`

### 2. Check Remote Clients Connectivity Status
This playbook checks connectivity between the Ansible controller and the remote hosts using the `ping` module.

- **File Name:** `check_connectivity.yml`
- **Purpose:** Verifies that all target hosts are reachable.
- **Key Task:**
    - Pings all remote hosts to check if they are online.

### 3. Copy File from Local to Remote Clients

This playbook copies a file from the Ansible controller to all target hosts.

- **File Name:** `copy_file.yml`
- **Purpose:** Copies a configuration file (`some.cfg`) from the local machine to the `/tmp` directory on all remote hosts with proper ownership and permissions.
- **Key Task:**
  - Copies `some.cfg` from `/home/iafzal` on the controller to `/tmp` on the remote machines.
  - Sets file ownership to `iafzal` and permissions to `0644`.



### 4. Playbook: Change File Permissions

This playbook modifies the permissions of a file or directory located at `/home/iafzal/linux2` on all specified hosts.

- **File Name:** `change_file_permissions.yml`
- **Purpose:** Updates the file permissions to allow all users (owner, group, and others) to write to the file or directory.
- **Key Task:**
  - Changes the permissions of `/home/iafzal/linux2` to `a+w`, which grants write access to all users.

### 5. Playbook: Setup HTTPD and Open Firewall Port

This playbook performs the following tasks on all target hosts:
1. Installs the Apache HTTP server package.
2. Starts the Apache HTTP server.
3. Opens port 80 for HTTP access in the firewall.
4. Reloads the firewall to apply the changes.

- **File Name:** `setup_httpd_firewall.yml`
- **Purpose:** Automates the setup of an Apache HTTP server and configures firewall settings to allow HTTP traffic.
- **Key Tasks:**
  - Installs the `httpd` package if not already present.
  - Ensures the `httpd` service is running.
  - Enables HTTP access by opening port 80 through the firewall.
  - Reloads the `firewalld` service to apply the firewall changes.

### 6. Playbook: Find and Kill a Process

This playbook performs the following actions on the target host (`10.253.1.115`):
1. Searches for the process named `top` on the remote host.
2. Retrieves the process ID (PID) of the identified processes.
3. Kills the processes based on the retrieved PIDs.

- **File Name:** `find_and_kill_process.yml`
- **Purpose:** Finds a process named `top` running on the remote system, retrieves its process ID, and kills it.
- **Key Tasks:**
  - Uses the `ps` command to get the PID of the `top` process.
  - Terminates the process using the `kill` command.

### 7. Playbook: Run Shell Script

This playbook runs a specified shell script located at `/home/iafzal/cfile.sh` on all target hosts.

- **File Name:** `run_shell_script.yml`
- **Purpose:** Executes the `cfile.sh` script located in the `/home/iafzal/` directory on all defined hosts.
- **Key Task:**
  - Runs the shell script `/home/iafzal/cfile.sh`.

### 8. Playbook: Download Tomcat

This playbook performs the following tasks on the local machine:
1. Creates the directory `/opt/tomcat` with appropriate permissions.
2. Downloads the Tomcat archive from the official Apache Tomcat website.

- **File Name:** `download_tomcat.yml`
- **Purpose:** Sets up the directory structure and downloads the Tomcat tar.gz file for installation.
- **Key Tasks:**
  - **Create Directory:** Ensures the directory `/opt/tomcat` exists with the specified permissions and ownership.
  - **Download Tomcat:** Fetches the Tomcat tar.gz file and places it in the created directory.
