# PAN-OS Upgrade to version 10.0.0

Upgrades a newly deployed VM-series to version 10.0.0


## What this does

This playbook will take a newly deployed VM-series and perform the following steps:
* install an auth-code and ensure this firewall is licensed
* Check for, download, and install the latest dynamic content
* Upgrade this firewall to 9.0.8 if necessary
* Upgrade this firewall to 9.1.3-h1 if necessary
* Upgrade this firewall to 10.0.0 


## Running

You will need a valid auth-code in order to perform the dynamic content updates and pull the latest software updates.

```bash

ansible-playbook -i inventory.yml -e 'username=admin' -e 'password=Super! Secret!' -e 'ip_address=192.168.1.55' -e 'auth_code=IBADCODE' upgrade_panos_v10.yml

```

## Tips and tricks

Build a virtual environment for this project:

```bash

apt install python3-venv
python3 -m venv .venv
. ./.venv/bin/activate
pip install ansible

```