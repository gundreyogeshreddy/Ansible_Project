# Ansible_Project

𝘼𝙣𝙨𝙞𝙗𝙡𝙚 : 
Ansible is a open source configuration management tool used to automate infrastructure and configuration management ,using ansible we can configure multiple servers at a time with just one single command.

𝙃𝙤𝙬 𝙞𝙩'𝙨 𝙬𝙤𝙧𝙠𝙨 :
Ansible uses playbook which is written in YAML syntax where we can define all our tasks and configurations that we want to apply on servers.
And we need inventory file or host file which consists of IP addressess of all the servers,on which we want to run the playbooks.
After we have the playbooks and defined the servers in the inventory file,we can run the ansible command which will run the playbook on the all servers defined in the inventory file using ssh.This is how ansible can be used to manage and configure multiple servers at once.✅



Task : Install and Start nginx on target server.
I'm using MobaXterm terminal and below are the steps to run the nginx on target server,
* * Steps :
* Install ansible and password less authentication required.
  
=> sudo apt update

=> sudo apt install ansible

=> ansible --version 

=> ssh-keygen

=> ls /home/ubuntu/.ssh/ (or) ls ~/.ssh/

=> cat ~/.ssh/id_rsa.pub

* Steps completed in Target Server,
=> ssh-keygen

=>  ls /home/ubuntu/.ssh/ (or) ls ~/.ssh/

=> vim ~/.ssh/authorized_keys ->now copy and paste the content from keygen ".pub content" to here in target server authorized_keys and save it.

=> Now in ansible_server,ssh to target server (ssh target-ip address)

=> Now,Password less authentication set up is completed,password less authentication is mandatory to ansible to configure another server for configuration management purpose.

* For one or two tasks "ansible adhoc commands" are good to use and for the multiple tasks we should write "ansible-playbooks" which are written in "yaml" syntax.
  
=> vim inventory_file (in this file copy and paste the target_server ip-address)

* ansible adhoc command to create file in target server.

=> ansible -i inventory_file all -m "shell" -a "touch first_file"(Now we can see the first_file is created in the target server)

* Now write the ansible-playbook which is in yaml syntax

=> vim first-playbook.yml(first-playbook is available in this repository,insert and save it)

=> ansible-playbook -i inventory_file first-playbook.yml(which runs the ansible playbook and install and starts nginx)

* Now in Target-Server

=> sudo systemctl status nginx (which shows the status of nginx is running)

* Now in ansible-server,to learn ansible in a better way use verbose (-vvv) for ansible and to understand what ansible is doing internally.

=> ansible-playbook -vvvvv -i inventory_file first-playbook.yml (To understand what's happening when we run the playbook.We can run it with the verbose (-v) extra "v" provides more debug output to the users).

=> Finally,nginx server is running on the target-server ✅
