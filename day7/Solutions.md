DAY 7 ANSIBLE

Assignment 1

Using Ansible Modules, Create Swap memory using swap File if Swap does not exist in the node machine , if it exists increase the swap Size.

Solution :-

First, I did the whole process manually.

I checked the swap space on my vagrant node by using command “free -h”.

Created a swap file using command  module of ansible & using

dd if=/dev/zero of=/test/swpfl bs=10M count=1

Setup the swap file using

mkswap /test/swpfl

For making the file more secure i give permissions to the file as 600.

Enabled the swpfl file using  swapon /test/swpfl command

Added the file permanently by adding it to fstab file.

Enabled the swap space using swapon -a.

A 9.2M swap space made on the node using ‘dd’ but its not used to make swap space for more than 1GB then we can use fallocate 
command.

Then I created the playbook by giving hosts -> node2 and created various task according to study from google and performing it 
manually with snapshots.





1. YML File

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day7%20images/swpyml.png)


2. YML Output

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day7%20images/swprun.png)


3. SWAP Space on Node2

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day7%20images/swpadd.png)


4. Error for creating 1GB swap space with dd command

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day7%20images/errordd.png)
