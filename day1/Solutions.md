DAY 1 ANSIBLE

Assignment 1
1. Use pip to install the ansible package and its dependencies to your control machine. 
```
# sudo apt-get install python-pip
# pip install jinja2
# pip install pyYAML
# pip install paramiko
# pip install ansible
```

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day1%20image/pipans.png)




2. Display the Ansible version and man page to STDOUT.
 
![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day1%20image/version.png)



3. Check all the possible parameters you need to know in ansible.cfg file. 
Here are some important possible parameter in ansible.cfg :-
- Inventory file path - /etc/ansible/hosts
- Forks – 5 (by default)
- Roles path - /etc/ansible/roles
- Host key checking – false
- Remote user – root
- Log path - /var/log/ansible.log
- Plugins path - /usr/share/ansible/plugins/*
- retry_files_save_path = ~/.ansible-retry

 

4. Ansible Inventory: Check the default inventory file for ansible control master and use inventory, run ansible ping commands on various inventory groups. Try this on minimum of two virtual machines.(You can use any of these Docker/Vagrant) 

- Created a master – 192.168.33.16
- Created a slave1 – 192.168.33.17
- Created a slave2 – 192.168.33.18
- Intalled Ansible on master and created ssh connection between them by using public key of master.
- Given the IP adresses of both the slaves in “/etc/ansible/hosts” file.
- Run the command
```
# ansible -m ping all
```
output :-

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day1%20image/pingpong.png)




5. In ~/.ansible.cfg file (create the file if it doesn't exist already) do the following: 
Create a new directory ~/.ansible/retry-files and set retry_files_save_path to it. 
Set the Ansible system forks to 10 
```
# cd ~
# touch .ansible.cfg
# cd .ansible
# mkdir retry-files
# cd ..
# sudo vim .ansible.cfg
```
[defaults]
retry_files_save_path = ~/.ansible/retry-files
forks = 5

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day1%20image/ansible.cfg.png)





