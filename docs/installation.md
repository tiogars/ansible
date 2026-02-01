# Ansible Installation Guide

## What is Ansible?

Ansible is an open-source automation tool that simplifies configuration management, application deployment, and task automation. It uses a simple, human-readable language (YAML) and doesn't require agents on managed nodes.

## Prerequisites

- Python 3.8 or higher
- SSH access to target hosts (for remote management)
- sudo/root privileges on control node

## Installation Methods

### Method 1: Using pip (Recommended)

```bash
# Install Ansible using pip
pip install ansible

# Verify installation
ansible --version
```

### Method 2: Using Package Manager

#### Ubuntu/Debian
```bash
sudo apt update
sudo apt install ansible -y
```

#### CentOS/RHEL
```bash
sudo yum install epel-release -y
sudo yum install ansible -y
```

#### macOS
```bash
brew install ansible
```

### Method 3: Using Python Virtual Environment (Best Practice)

```bash
# Create a virtual environment
python3 -m venv ansible-venv

# Activate the virtual environment
source ansible-venv/bin/activate  # On Linux/macOS
# ansible-venv\Scripts\activate   # On Windows

# Install Ansible
pip install ansible

# Verify installation
ansible --version
```

## Verify Installation

After installation, verify that Ansible is properly installed:

```bash
ansible --version
```

You should see output similar to:
```
ansible [core 2.xx.x]
  config file = None
  configured module search path = [...]
  ansible python module location = [...]
  executable location = /usr/local/bin/ansible
  python version = 3.x.x
```

## Next Steps

After installing Ansible, proceed to the [Getting Started Guide](getting-started.md) to learn how to use it.
