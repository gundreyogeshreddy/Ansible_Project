# Ansible_Project

𝘼𝙣𝙨𝙞𝙗𝙡𝙚 : 
Ansible is a open source configuration management tool used to automate infrastructure and configuration management ,using ansible we can configure multiple servers with just a single command. 

𝙃𝙤𝙬 𝙞𝙩'𝙨 𝙬𝙤𝙧𝙠𝙨 :
Ansible uses playbook which is written in YAML syntax where we can define all our tasks and configurations that we want to applied on the all servers.
And we need inventory file or host file which consists of IP addressess of all the servers,on which we want to run the playbooks.
After we have the playbooks and defined the servers in the inventory file,we can run the ansible command which will run the playbook on the all servers defined in the inventory file using ssh.This is how ansible can be used to manage and configure multiple servers at once.✅



Task : Install and Start nginx on target server
I'm using MobaXterm terminal and below are the steps to run the nginx on target server,
* Steps Completed in ANSIBLE_SERVER,
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

* For one or two tasks "ansible adhoc commands" are good to use and for the multiple tasks we should write "ansible-playbooks" which are written in "yaml" syntax
