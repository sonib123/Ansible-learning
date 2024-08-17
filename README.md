# Ansible Playbooks for Localhost

This repository contains a set of simple Ansible playbooks designed to run on the localhost. These playbooks serve as examples for basic tasks such as testing connectivity, printing output, combining tasks, and installing services.

## Playbooks Overview

1. **Ping Localhost (`first.yml`)**  
   This playbook tests connectivity by pinging the localhost. It's a straightforward example to ensure that your Ansible setup is correctly configured and can communicate with the local machine.

2. **Hello World (`helloworld.yml`)**  
   This playbook prints "Hello World" to the terminal. It's a basic demonstration of how to use Ansible to run simple commands on the localhost.

3. **Combined Tasks (`mstask.yml`)**  
   The `mstask.yml` playbook combines the tasks from the previous two playbooks into one. It first tests the connectivity by pinging the localhost and then prints "Hello World" to the terminal.

4. **Package Installation (`packinstall.yml`)**  
   This playbook installs the Apache HTTP server (`httpd` package) and starts the service on the localhost. It ensures that the Apache server is running and ready to serve web pages.

## Usage

To run these playbooks, ensure you have Ansible installed on your machine. Clone this repository, navigate to the directory containing the playbooks, and run them using the `ansible-playbook` command:

```bash
ansible-playbook first.yml
ansible-playbook helloworld.yml
ansible-playbook mstask.yml
ansible-playbook packinstall.yml
