# PAN-OS Upgrade to version 10.0 Beta

Upgrades a newly deployed VM-series to version 9.2.0b46 (soon to be 10.0)

## Running

```bash

ansible-playbook -i inventory.yml -e 'username=admin' -e 'password=Super! Secret!' -e 'ip_address=192.168.1.55' -e 'panos_image_path=/srv/nfs/images/PanOS_vm-9.2.0-b46.qcow2' -e 'auth_code=IBADCODE' upgrade_panos_v10.yml

```

## Tips and tricks

Build a virtual environment for this project:

```bash

apt install python3-venv
python3 -m venv .venv
. ./venv/bin/activate
pip install ansible

```