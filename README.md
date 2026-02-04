# POC Infrastructure deployment
**DISCLAIMER : DO NOT USE THIS PLAYBOOK IN PROD AS IT IS. POC ONLY USAGE**
## Purposes

This repo aims to automate the deployment of our IoMT POC inventory through an Ansible playbook.

The playbook provides basic installation required for GLPI, OCSInventoryNG and TapirX use.

To make this configuration operative, the installation includes:

- Apache2 web server installation and configuration
- MariaDB database server installation and configuration
- PHP8.4 installation
- Go installation
- GLPI server installation and configuration
- OCS server installation and configuration
- TapirX installation

What still needs to be done to complete deployment:

- Manual OCS plugin install from GLPI marketplace
- Manual GLPI-OCS connection once plugin is installed (need to set TRACE_DELETE = ON from OCS server before connecting the plugin)

## Playbook use

- Create **Deployer** user on target machine:
```bash
sudo adduser deployer
sudo usermod -aG deployer sudo
```

- Add passwordless sudo to deployer:
```bash
echo "deployer ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/deployer
chmod 440 /etc/sudoers.d/deployer
```


- Clone this repo using git clone on Ansible master:
```bash
git clone https://github.com/Bolo101/labDeployment.git
```

- Get in the Ansible project:
```bash
cd labDeployment/
```

- Change target IP in inventory.ini based on you target IP address

- Run playbook:
```bash
ansible-playbook -i inventory.ini playbook.yml
```
