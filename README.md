# Ansible-apps-deploy-Arch/Garuda

By default, on Garuda Linux, the default directory for storing playbook files and other Ansible-related files is `/etc/ansible`.                                                                                                                          

Within this directory, the following folders are commonly used:

1. **/etc/ansible/inventory**: This directory contains inventory files, which list the remote hosts that Ansible will run against.                                                                                                                              

2. **/etc/ansible/playbooks**: This directory contains Ansible playbooks, which are YAML files that define the tasks to be executed by Ansible.                                                                                                                 

3. **/etc/ansible/roles**: This directory is used to store Ansible roles, which are a way to group together tasks, handlers, and templates.                                                                                                                     

You can use these default directories for your Ansible project, or you can create a new directory structure that suits your needs. In the instructions I provided earlier, we created a new directory named `garuda-ansible` to store our playbook and inventory file.                                                                                                                          

I hope that helps!

＄in that case, rewrite the earlier instructions so that they work with the directory structure that you just provided      2454
Sure thing! Here are the updated instructions to use the default Ansible directory structure on Garuda Linux:

1. On your local machine, create a new directory under `/etc/ansible` to store your project files. For example, you could create a directory named `garuda-deployment`:                                                                                         

   ```
   sudo mkdir /etc/ansible/garuda-deployment
   ```

2. Change your working directory to the new project directory:

   ```
   cd /etc/ansible/garuda-deployment
   ```

3. Create a new file named `hosts` in the `garuda-deployment` directory and populate it with the following:

   ```
   [garuda-linux]
   192.168.0.25
   ```

   Make sure to replace `192.168.0.25` with the actual IP address of your Garuda Linux machine. Save and close the file.

4. Create a new file named `install-software.yml` in the `garuda-deployment` directory. Copy and paste the playbook I shared with you earlier into this file and save it.                                                                                       

5. Run the playbook to install the software on the remote Garuda Linux machine:

   ```
   ansible-playbook install-software.yml -i hosts -u your_remote_username -K
   ```

   Replace `your_remote_username` with the username you use to log into your Garuda Linux machine.

   Ansible will prompt you for the `sudo` password for your Garuda Linux machine, so enter it when prompted.

   Ansible should now begin installing the software packages you listed on the remote machine. This may take some time depending on your internet connection speed and the number of packages you are installing.
