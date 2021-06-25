DAY 5 ANSIBLE

Assignment 1
All needs to be done using ansible modules with jenkins There will be three jenkins jobs, Provisioning, Build, Deployment.
Provisioning:-
1. Provision application servers, for example - java, tomcat are required for a java project. 
2. This job will be a separate job and can be executed to any machine on requirement. 
Build and Deployment Job will be in downstream relationship.
Build:-
1. Build any Project - can be java or any other language using jenkins. 
Deployment:-
1. Create a down stream deployment job to the build job . 
2. In the deployment job , deploy the artifact (war in case of java) to the application server (tomcat/joboss) using ansible in the downstream job. 
3. Ansible play book will include health check also, (status code == 200) , if health check fails, job should also fail. 






SOLUTION :-
1. Provision YML file

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day5%20images/provisionyml.png)

2. Provision Success file

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day5%20images/provisionsuccess.png)

3. Provision Jenkins file

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day5%20images/provisionjenkins.png)

4. Build YML file

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day5%20images/buildyml1.png)

5. Build Success file

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day5%20images/buildsuccess.png)

6. Build Jenkins file

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day5%20images/buildjenkins.png)

7. Deploy YML file

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day5%20images/deployyml.png)

8. Deploy Success file

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day5%20images/deploysuccess.png)

9. Deploy Jenkins file

![Job DSL Plugin](https://github.com/lovedeepsh/ansible/blob/master/ansible%20day5%20images/deploymentjenkins.png)
