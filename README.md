# sui-boot
The sui-boot repository contains an ansible playbook designed to efficiently set up a SUI validator on an Ubuntu bare metal server.

## pre requisites:
Before using sui-boot, ensure the following prerequisites are met:
* Ansible is installed.
* The user has sudo privileges.
## Tested on Latitude.sh Bare Metal Server c3.large.x86
sui-boot has been thoroughly tested on the Latitude.sh bare metal server using the c3.large.x86 configuration. This ensures the compatibility and reliability of the playbook on this specific platform.
## inventory
The repository includes the following inventory files:
* testnet.yaml
* mainnet.yaml
## Quick start
To quickly set up a SUI validator, follow these steps:
1. Clone the sui-boot repository and navigate to the cloned directory:
```shell
git clone https://github.com/manystake/sui-boot.git && cd sui-boot
```
2. Execute the ansible playbook using the appropriate inventory file (e.g., testnet.yaml). Specify the target host as "local" and use the local connection option. Finally, update the message of the day (MOTD) with sudo privileges:
```shell
ansible-playbook -i inventory/testnet.yaml boot.yaml -e host=local --connection=local && sudo update-motd
```
3. After the playbook execution is complete, the MOTD will display instructions on how to proceed with the installation. Follow the instructions provided to finish the installation process.