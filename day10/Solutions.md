DAY 10 ANSIBLE

Assignment 1

Create Ansible Roles for Nginx, Tomcat, Java. 
Roles should run on at least two different OS - For Ex - Ubuntu and Centos. 
It should include Templates for the configuration files with all the dynamic value that needs to be updated. 
It should include handlers , but not along with the task. 
At the end of Role, it should print the current state of Nginx and tomcat . 
Roles execution should be only through jenkins . 
Jenkins will pull the updated role every time from Git only. 
User can select which role he/she want to execute from jenkins - tomcat/nginx/java . 
User should have the options to execute the role on centos or ubuntu or together on both. 
Java role should be available separately for tomcat's dependency and will be executed when tomcat role executes using meta and also should have option to run separately from jenkins. 




Java Role run: 

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day10%20images/javarolerun.png)

Nginx Role run:

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day10%20images/nginxrun.png)





1. Java role

https://github.com/lovedeepsh/ansible/tree/master/day10/java


2. Nginx role

https://github.com/lovedeepsh/ansible/tree/master/day10/nginx


3. Tomcat role

https://github.com/lovedeepsh/ansible/tree/master/day10/tomcat
