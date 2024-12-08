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

## Elevate sudo
```bash
ansible all -m apt -a update_cache=true --become --ask-become-pass
ansible all -m apt -a name=vim-nox --become --ask-become-pass
ansible all -m apt -a "name=snapd state=latest" --become --ask-become-pass
ansible all -m apt -a "upgrade=dist" --become --ask-become-pass
```

## Ansible Playbooks
```bash
ansible-playbook --ask-become-pass ./playbooks/install_apache.yaml
ansible-playbook --ask-become-pass ./playbooks/uninstall_apache.yaml

```

## References
- "Getting started with Ansible" https://www.youtube.com/watch?v=4REljLsOnXk&list=PLT98CRl2KxKEUHie1m24-wkyHpEsa4Y70