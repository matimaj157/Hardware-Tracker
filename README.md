### Ansible reporter ###
This playbook is meant to provide information about servers' parameters such as:
- Reachability
- Hostname 
- Distro
- Serial Nr
- Product name
- Users
- Drives information
- PCI devices
- Network Devices details
- VMs on QEMU
- Available updates
- Last update date

When all pieces of information are gathered, html file will be created containing all data structured as a table with the ability to hide specific columns for better visibility and readability.

Requiered dependencies:
- python3
- ansible
- sshpass

How to use:
1. Download all files and place them in the folder in which you would like to generate your report.
2. Prepare an inventory file in .ini or .yml extension and place all hosts under the "servers" group, you also have to provide a username, passwd and root password for each host (or for a group of hosts, as it is shown in example.ini file). You can also create your own group of hosts and change the target group in reporter.yml file.
3. Run the playbook with the specified inventory file, you can use the following command: "ansible-playbook -i inventory.ini reporter.yml"

After running this command ansible will start to gather the detailes mentioned above, don't worry if you see loads of errors, in this scenario it's totally normal behavior, depending on how many hosts you are scanning, execution of this playbook may take up to a few minutes.
