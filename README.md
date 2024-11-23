# Ansible Project

This is a test repository for all the playbooks. 

## Setup 
Install Ansible
```bash
sudo apt update
sudo apt upgrade -y
sudo apt install ansible -y
```
Create inventory file and execute ansible to connect to the servers in inventory.
```bash
ansible all --key-file ~/.ssh/id_ed25519 -i inventory -m ping
ansible all -i inventory -m ping
ansible all --list-hosts
ansible all -m gather_facts
ansible all -m gather_facts --limit <ipAddress>
```