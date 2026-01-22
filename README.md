# POC Infrastructure deployment

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

What still needs to be done:

- Manual OCS plugin install from GLPI marketplace
- Manual GLPI-OCS connection once plugin is installed (need to set TRACE_DELETE = ON from OCS server before connecting the plugin)