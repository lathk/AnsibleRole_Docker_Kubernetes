Docker and Kubernetes Deployment with Ansible on Ubuntu.

## Prerequisite
1) Ansible Controller 
    1) Ubuntu node with Ansible installed with necessary roles added accordingly.

2) Kubernetes:
    1) Minimum two Ubuntu nodes [One master and one worker node]. You can have more worker nodes as per your requirement.
    2) The master node should have a minimum of 2 vCPU and 2GB RAM.
    3) For the worker nodes, a minimum of 1vCPU and 2 GB RAM is recommended.

## installation Instructions:

1) Configure ssh-key based authentication for passwordless login on all the hosts and verify passwordless authentication.
2) install necessary components on all the hosts: ssh tools, net-tools, sshpass
3) create a folder for Ansible within which add inventory.txt and the main playbook.yml (Creating a folder here is optional).
3) Configure roles on the Ansible controller node for Docker, Kube-file, kube-user, kube-master & Kube-worker.
4) Add the tasks under tasks foler within yml file for each roles created for its respective tasks to be accomplished.
5) Once the necessary details are configured, run the below command to execute the task using playbook.

#ansible-playbook playbook.yml --extra-vars "ansible_ssh_user=root" -i inventory.txt

Note: --extra-vars is optional here.
6) Once the tasks are executed login to the user created for kubernetes deployment and validate the deployment using the command #kubectl get nodes 
