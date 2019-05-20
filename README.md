# WireGuard Ansible role

Status: alpha, work in progress

A very simple Ansible role to install [WireGuard](https://www.wireguard.com/).

## Python environment for Ansible

```
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

## Install wireguard on remote host

Example:

```
ansible-playbook -i "wg1.example.com," -u ubuntu -b -vv playbook-wireguard.yml
```

## Install wireguard on localhost

```
source venv/bin/activate
ansible-playbook -i "localhost," -b -K -c local -vv playbook-local.yml
```

## Testing with Vagrant

```
source venv/bin/activate
vagrant up
```
