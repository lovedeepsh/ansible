DAY 3 ANSIBLE

Assignment 1
1. Create and delete ninja directory on host machine
- Created
```
#  ansible all -a "mkdir /home/vagrant/ninja"
```
- Deleted
```
# ansible all -a "rmdir /home/vagrant/ninja"
```

2. Set hostname on all nodes from remote machine
```
# ansible all -a "sudo hostname lovedeep"
``` 
![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day3%20images/hostname.png)

3. Fetch os of all nodes and store o/p into a file, use min two different machine of different flavour of os.
```
# ansible all -m setup -a 'gather_subset=virtual' | grep os_family > /home/vagrant/love1
```

output :-
![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day3%20images/os-output.png)
![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day3%20images/os-output2.png)

 
4. Add three group into hosts file through ansible module. 
          Debian ( ip of debian machine)
          Centos ( ip of centos machine)
          All ( ip of all nodes )
```
# ansible localhost -m lineinfile -u root -a "path=/etc/ansible/hosts line=[Debian]\n192.168.33.14\n[Centos]\n192.168.33.24\n[All]\n192.168.33.14\n192.168.33.24"
```






Problem statement: Using Adhoc command
Step 1:
    * Install apache on Debian machine
```
# ansible Debian -m apt -u root -a “name=apache2 state=present”
```

\    * Cross check apache isntalled or not from remote machine
```
# ansible Debian -a "sudo systemctl status apache2"
```
\    * Apache runn  on 8082 port
```
# ansible Debian -m lineinfile -u root -a "path=/etc/apache2/ports.conf state=present regexp='Listen 80' line='Listen 8082'"
```
 \   * Create two virtual host
 \   * Restart apache from remote machine
Step2:

   * Install nginx on centos machine
```
# ansible Centos -m yum -u root -a “name=nginx state=present”
```

   * Nginx run on 8080 port.
```
# ansible Centos -m lineinfile -u root -a "path=/etc/nginx/nginx.conf state=present regexp='listen       80 default_server;' line='listen       8080 default_server;'"
```
```
# ansible Centos -m lineinfile -u root -a "path=/etc/nginx/nginx.conf state=present regexp='listen       [::]:80 default_server;' line='listen       [::]:8080 default_server;'"
```
![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day3%20images/nginx8080.png)


Step3:
   * Configure Nginx - configure it to run as reverse proxy to apache
