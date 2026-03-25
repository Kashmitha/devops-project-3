# DevOps Project 3 — Ansible Configuration Management on Azure

![Ansible CI](https://github.com/Kashmitha/devops-project-3/actions/workflows/ansible.yml/badge.svg)

## Overview
Automated configuration management of Azure Linux VMs using Ansible Core 2.20
with role-based playbook architecture, dynamic inventory, and security hardening.

## Tech Stack
- Ansible Core 2.20.3 + ansible 11.3.0
- azure.azcollection 3.14.0
- Azure VM: Standard_DC2ads_v5 (Ubuntu 22.04 LTS)
- Nginx (reverse proxy), Docker (app container)
- UFW + fail2ban (security hardening)
- GitHub Actions (CI/CD - lint + syntax check)

## Roles
| Role     | Purpose                              |
|----------|--------------------------------------|
| common   | System update, packages, users       |
| security | UFW, fail2ban, SSH hardening         |
| docker   | Docker Engine installation           |
| nginx    | Reverse proxy configuration          |

## Usage
```bash
# 1. Provision VM
ansible-playbook playbooks/provision_vm.yml

# 2. Configure server
ansible-playbook playbooks/configure_all.yml

# 3. Deploy app
ansible-playbook playbooks/deploy_app.yml

# 4. Teardown
ansible-playbook playbooks/teardown.yml
```

## Key Concepts Demonstrated
- Idempotent playbooks
- Role-based architecture
- Dynamic Azure inventory
- Jinja2 templates
- Ansible handlers
- Security hardening automation

## Author
Kashmitha Madushan Gamini— DevOps Engineer (Intern)

This project is licensed under the MIT License — see the LICENSE file for details.
