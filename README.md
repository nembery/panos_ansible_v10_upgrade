# PAN-OS Upgrade to version 10.0 Beta

Upgrades a newly deployed VM-series to version 9.2.0b46 (soon to be 10.0)


## What this does

This playbook will take a newly deployed VM-series and perform the following steps:
* install an auth-code and ensure this firewall is licensed
* Check for, download, and install the latest dynamic content
* Upgrade this firewall to 9.0.8 if necessary
* Upgrade this firewall to 9.1.2-h1 if necessary
* Upload the 9.2.0-b46 software image to the firewall
* Upgrade this firewall to 9.2.0-b46 (Version 10.0 Beta)


## Running

First, sign into https://support.palooaltonetworks.com and download the Latest 9.2 Beta image for VM-Series.
Place this file somewhere that is accessible to your Ansible installation.

```bash

ansible-playbook -i inventory.yml -e 'username=admin' -e 'password=Super! Secret!' -e 'ip_address=192.168.1.55' -e 'panos_image_path=/mnt/images/PanOS_vm-9.2.0-b46' -e 'auth_code=IBADCODE' upgrade_panos_v10.yml

```

## Tips and tricks

Build a virtual environment for this project:

```bash

apt install python3-venv
python3 -m venv .venv
. ./venv/bin/activate
pip install ansible

```