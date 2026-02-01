# Getting Started with Ansible

## Overview

This guide will help you get started with Ansible by creating a simple inventory and running your first playbook.

## Basic Concepts

### Inventory
An inventory file defines the hosts and groups of hosts that Ansible can manage. It can be in INI or YAML format.

### Playbook
A playbook is a YAML file that defines a set of tasks to be executed on specified hosts.

### Modules
Modules are the units of work in Ansible. Examples include `ping`, `copy`, `yum`, `apt`, etc.

## Quick Start

### 1. Set Up Your Inventory

Create an `inventory.yml` file in your project root (see [inventory.yml](../inventory.yml) in this repository for an example).

Example inventory structure:
```yaml
all:
  hosts:
    localhost:
      ansible_connection: local
  children:
    webservers:
      hosts:
        web1:
          ansible_host: 192.168.1.10
        web2:
          ansible_host: 192.168.1.11
    databases:
      hosts:
        db1:
          ansible_host: 192.168.1.20
```

### 2. Test Connectivity

Test that Ansible can connect to your hosts:

```bash
# Test localhost
ansible all -i inventory.yml -m ping

# Test specific group
ansible webservers -i inventory.yml -m ping
```

### 3. Create Your First Playbook

Create a `playbook.yml` file (see [playbook.yml](../playbook.yml) in this repository for an example).

Example playbook:
```yaml
---
- name: My First Playbook
  hosts: all
  tasks:
    - name: Ensure a file exists
      ansible.builtin.file:
        path: /tmp/ansible-test
        state: touch
```

### 4. Run Your Playbook

Execute your playbook:

```bash
ansible-playbook -i inventory.yml playbook.yml
```

## Common Commands

### Ad-hoc Commands
Run single tasks without writing a playbook:

```bash
# Check disk space
ansible all -i inventory.yml -a "df -h"

# Install a package
ansible webservers -i inventory.yml -m apt -a "name=nginx state=present" --become

# Copy a file
ansible all -i inventory.yml -m copy -a "src=/local/file dest=/remote/file"
```

### Playbook Commands

```bash
# Run a playbook
ansible-playbook -i inventory.yml playbook.yml

# Dry run (check mode)
ansible-playbook -i inventory.yml playbook.yml --check

# Verbose output
ansible-playbook -i inventory.yml playbook.yml -v

# Run specific tags
ansible-playbook -i inventory.yml playbook.yml --tags "configuration"
```

## Best Practices

1. **Use version control**: Keep your inventory and playbooks in Git
2. **Use variables**: Store configuration in variables for reusability
3. **Use roles**: Organize complex playbooks into reusable roles
4. **Test before production**: Use `--check` mode to test changes
5. **Use vault for secrets**: Encrypt sensitive data with `ansible-vault`

## Directory Structure

A typical Ansible project structure:

```
ansible-project/
├── inventory.yml
├── playbook.yml
├── ansible.cfg
├── group_vars/
│   └── all.yml
├── host_vars/
│   └── web1.yml
├── roles/
│   └── webserver/
│       ├── tasks/
│       ├── handlers/
│       ├── templates/
│       └── files/
└── docs/
    ├── installation.md
    └── getting-started.md
```

## Useful Resources

- [Official Ansible Documentation](https://docs.ansible.com/)
- [Ansible Galaxy](https://galaxy.ansible.com/) - Share and find roles
- [Ansible Examples](https://github.com/ansible/ansible-examples)

## Next Steps

1. Explore the [inventory.yml](../inventory.yml) and [playbook.yml](../playbook.yml) files in this repository
2. Modify them to match your infrastructure
3. Try running the example playbook
4. Learn about [Ansible Roles](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html)
5. Explore [Ansible Galaxy](https://galaxy.ansible.com/) for pre-built roles
