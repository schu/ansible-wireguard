# Wireguard Ansible role (experimental)

## Python environment

```
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

## Install wireguard on localhost

```
source venv/bin/activate
ansible-playbook -i "localhost," -b -K -c local -vv playbook-local.yml
```

## Test in Vagrant

```
source venv/bin/activate
vagrant up
```
