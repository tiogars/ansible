# ansible
Documentation to start faster with Ansible

## Quick Start

This repository contains documentation and example files to help you get started with Ansible.

### Documentation

Visit the [docs](docs/) folder for comprehensive guides:
- [Installation Guide](docs/installation.md) - How to install Ansible
- [Getting Started Guide](docs/getting-started.md) - Learn the basics of Ansible

### Example Files

- **inventory.yml** - Sample inventory file with various host groups
- **playbook.yml** - Example playbook demonstrating common Ansible tasks

### Running the Example

1. Install Ansible (see [Installation Guide](docs/installation.md))
2. Test the example playbook on localhost:
   ```bash
   ansible-playbook -i inventory.yml playbook.yml --limit localhost
   ```

For more information, check out the [documentation](docs/).

