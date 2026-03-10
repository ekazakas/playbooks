# playbooks

Ansible playbooks for Arch Linux local environment setup.

## Prerequisites

```bash
sudo pacman -S git ansible
```

## Usage

```bash
ansible-playbook -i inventory/localhost site.yml -K
```
