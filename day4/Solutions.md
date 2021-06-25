DAY 4 ANSIBLE

Assignment 1
1. Create an Ansible playbook that targets members of the "app" group has the following state:
2. The tomcat7 is installed in all host 
3. Has the war file in webapps folder specified in appwar. 
4. Tomcat is started on each host. 
While developing the playbook use the --syntax-check to check your work and debug problems. Run your playbook in verbose mode using the -v switch to get more information on what Ansible is doing. Try -vv and -vvv for added verbosity. Also consider running --check to do a dry-run as you are developing.











---
 - hosts: Debian
   remote_user: root
   become: yes
   become_method: sudo
   vars:
    Final: 'Tomcat8 has been Installed'
   tasks:
   - name: Install Tomcat8
     apt:
       name: tomcat8
       state: present
   - name: Starting tomcat8.service
     service:
       name: tomcat8.service
       state: stopped
   - name: Copy war file to Tomcat webapps
     copy:
       src: /home/vagrant/warf/assignment/
       dest: /usr/share/tomcat8/webapps/
   - name: Starting tomcat8.service
     service: 
       name: tomcat8.service 
       state: started


![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day4%20image/playbookoutput.png)
![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day4%20image/-vvvv.png)


