# playbooks

Ansible playbooks for Arch Linux local environment setup.

## Prerequisites

```bash
sudo pacman -S git ansible ansible-lint
```

## Usage

```bash
ansible-playbook -i inventory/localhost site.yml -K
```
