DAY 2 ANSIBLE

Assignment 1
1. Fetch and display to STDOUT Ansible facts using the setup module. 

```
# ansible all -m setup
```

2. Fetch and display only the "virtual" subset of facts for each host.

```
# ansible all -m setup -a ‘gather_subset=virtual’ 
```

3. Fetch and display the value of fully qualified domain name (FQDN) of each host from their Ansible facts.
```
# ansible all -m setup  | grep fqdn
```

output :- "ansible_fqdn": "ubuntu-xenial",

4. Display the uptime of all hosts using the command module. 

```
# ansible all -a ‘uptime’
```
            output:- 
192.168.33.17 | SUCCESS | rc=0 >>
 09:49:19 up  2:42,  2 users,  load average: 0.00, 0.00, 0.00

5. Ping all hosts except the 'control' host using the --limit option
```
# ansible -m ping all - -limit 'Control' 
```

6. Setup Java8 on the hosts in the "App" group using the apt module. 
```
# ansible all -m apt_repository -u root -a “repo=ppa:webupd8team/java"
# ansible all -m command -a "sudo apt-get update"
# ansible all -m apt -u root -a "name=oracle-java8-installer state=present"
```

7. Setup and enable the EPEL package repository on the hosts in the "web" group using the yum module. 
CentOS systems use the latest epel-release package 
RHEL systems should use https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm 
Create inventory groups app and web 

```
# ansible Centos -m yum -u root -a "name=epel-release state=present"
```

11. set a cron on ansible control machine that will run every 1 minute , and perform below tasks:- 
execute ansible adhoc commands on client machines (cannot be control machine) , to create a file in /var/log/ninja_name on all the client nodes, append system_hostname [:space:] system_time in the file every 1 minute using ansible facts. 
