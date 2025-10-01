# Ansible Nexus Repository deployment

Ansible project that follows steps to deploy Nexus Repository OSS in a remote server.

## Features
- Install server package dependencies
- Download and unpack Nexus Repository OSS from source
- Enable and starts Nexus Repository service

## Usage
1. Change the `ansible.cfg` file:
```ini
; change the inventory line to place the absolute path to the inventory of this project on your control node:
inventory = /root/ansible-nexus-deployment/inventory.ini
```

2. Change the `inventory.ini` file:
```ini
; change 'ansible_host' to the IP address of each target host:
ansibt0 ansible_host=10.20.30.120

; set 'ansible_ssh_private_key_file' to the right path to private ssh file:
ansible_ssh_private_key_file=~/.ssh/id_nexus
```

3. Change the `vars.yaml` file:
```yaml
# Change root directory path to the absolute path to this project on your control node:
root:
  directory: /root/ansible-nexus-deployment
```

4. Run `ansible-playbook`:
```bash
ansible-playbook main.yaml
```