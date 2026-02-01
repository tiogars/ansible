# Documentation Index

Welcome to the Ansible documentation! This folder contains guides to help you get started with Ansible.

## Available Documentation

1. **[Installation Guide](installation.md)** - Learn how to install Ansible on various platforms
   - Prerequisites
   - Installation methods (pip, package managers, virtual environment)
   - Verification steps

2. **[Getting Started Guide](getting-started.md)** - Learn the basics of using Ansible
   - Basic concepts (Inventory, Playbooks, Modules)
   - Quick start guide
   - Common commands
   - Best practices
   - Project structure recommendations

## Quick Start

If you're new to Ansible:

1. Start with the [Installation Guide](installation.md) to set up Ansible
2. Read the [Getting Started Guide](getting-started.md) to understand core concepts
3. Examine the [inventory.yml](../inventory.yml) file in the repository root
4. Review the [playbook.yml](../playbook.yml) file for a working example
5. Run the sample playbook: `ansible-playbook -i inventory.yml playbook.yml --limit localhost`

## Repository Files

- `inventory.yml` - Sample inventory file with various host groups
- `playbook.yml` - Example playbook demonstrating common Ansible tasks

## Additional Resources

- [Official Ansible Documentation](https://docs.ansible.com/)
- [Ansible Galaxy](https://galaxy.ansible.com/)
- [Ansible GitHub Repository](https://github.com/ansible/ansible)
