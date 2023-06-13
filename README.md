# Ansible-apps-deploy-Arch/Garuda

1. Prerequisites:
   * You'll need to have installed Ansible on your local machine. If you don't have it, you can follow [these instructions](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) to install it on your machine.                  

   * You'll need to have `openssh` installed on both your local machine and the remote Garuda Linux machine, so that Ansible can connect to it. If you don't have it, you can install it using the following command:                                           
   
     ```
     sudo pacman -S openssh
     ```

2. On your local machine, create a new directory where you'll store the Ansible playbook and the inventory file for this project.                                                                                                                               

   ```
   mkdir garuda-ansible && cd garuda-ansible
   ```

3. Create a new file named `hosts.ini` in the `garuda-ansible` directory and populate it with the following:

   ```
   [garuda-linux]
   192.168.0.25
   ```

   Make sure to replace `192.168.0.25` with the actual IP address of your Garuda Linux machine. Save and close the file.

4. Create a new file named `install-software.yml` in the `garuda-ansible` directory. Copy and paste the playbook I shared with you earlier into this file and save it.                                                                                          

5. Run the playbook to install the software on the remote Garuda Linux machine:

   ```
   ansible-playbook install-software.yml -i hosts.ini -u your_remote_username -K
   ```

   Replace `your_remote_username` with the username you use to log into your Garuda Linux machine.

   Ansible will prompt you for the `sudo` password for your Garuda Linux machine, so enter it when prompted.

   Ansible should now begin installing the software packages you listed on the remote machine. This may take some time depending on your internet connection speed and the number of packages you are installing. 

NOTES

The default directory for storing playbook files and other Ansible-related files is `/etc/ansible`.                                                                                                                          

Within this directory, the following folders are commonly used:

1. **/etc/ansible/inventory**: This directory contains inventory files, which list the remote hosts that Ansible will run against.                                                                                                                              

2. **/etc/ansible/playbooks**: This directory contains Ansible playbooks, which are YAML files that define the tasks to be executed by Ansible.                                                                                                                 

3. **/etc/ansible/roles**: This directory is used to store Ansible roles, which are a way to group together tasks, handlers, and templates. 
