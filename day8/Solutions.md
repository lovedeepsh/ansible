DAY 8 ANSIBLE

Assignment 1

1. Create 5 users with password, and these five users should have same permissions for a directory named ninja.(Directory can be created with the 5 users permmission.)

2. Create ssh key for each user so that all those 5 users will be able to login through ssh.

Solution :-

Created 5 users

- Created a playbook named Usermanagement.yml

- For permission we can use ACL module in ansible

 - name: Grant user Joe read access to a file
 ```
    acl:
                 path: /home/vagrant/common_dir
                 entity: common_dir
                 etype: directory
                 permissions: r+w
                 state: present
```
Usermanagement Playbook


https://github.com/lovedeepsh/ansible/blob/master/day8/Usermanagement.yml



Usermanagement run

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day8%20images/Usermanagementrun.png)



3. Creat Logical Volume in any node machine.

4. need to installl lvm2 first using ansible.

5. Create ext4 type File System on the newly created logical volume.

6. Mount newly created file system.

LVM YML

https://github.com/lovedeepsh/ansible/blob/master/day8/lvol.yml



LVM RUN

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day8%20images/finalrun.png)


Trials :-

link - https://github.com/lovedeepsh/ansible/tree/master/ansible%20day8%20images


Modules Used :-

1. Usermanagement

- group

- user

- file 

2. LVOL

- apt

- lvg

- lvol

- filesystem

- file

- mount
