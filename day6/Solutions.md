DAY 6 ANSIBLE

Assignment 1
1. Create an Ansible playbook to rotate ssh keys. Explaination - Replacing the keys you’re currently using with new keys, and removing the ability for old keys to be used to log into your systems.
2. Create a new key 
3. Add new key to authorized_keys files on your nodes 
4. Test new key 
5. Remove previous keys from authorized_keys files on your nodes. 
6. again test the connectivity with the new keys. 

Solution :-
```
First, I tried to do the whole process manually.
1. Created 2 machines i.e. one ansble machine and one node.
2. Created ssh connection between them by providing ansible machines public key into nodes authorized_keys.
3. Checked ping:pong connection between them.
4. Created another pair of ssh keys and Performed the same process.
```

Now, For playbook i used a new pair of ssh keys in “/home/vagrant/test/.ssh/id_rsa1.pub”
Created a playbook and performed the functions using “authorized_keys” module.



-> PLAYBOOK

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day6%20images/sshyml.png)


-> RUNNING PLAYBOOK

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day6%20images/ssh.png)


-> TESTING AFTER PING-PONG

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day6%20images/afterping.png)
