# simple_grid_kube_cluster
Summer Project of Julia. Contains code to support Kubernetes via the SIMPLE Framework.

Description

Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications developed at Google. It has become highly popular among some of the largest distributed computing projects in recent years and currently is the market leader among its competitors. The SIMPLE framework’s modular architecture supports plug and play of different container orchestration technologies without disrupting its overall functionality. For these reasons, adding support for Kubernetes is both desirable and feasible.

Setup

The process of creating a Kubernetes cluster contains the following steps:
1.	Set ansible environment by creating ansible.cfg file, where you should put your private key.
2.	Create hosts.txt file where roles were set.
3.	Run kube-dependences.yml playbook, which installs Docker and some Kubernetes options such as kubelet, kubeadm on your master and workers machines.
4.	Run master.yml playbook by using a command “ansible-playbook -i hosts --ask-vault-pass master.yml”. So, put there a vault-password to add the user centos with a primary group.
5.	Run workers.yml playbook to expand site admin’s action on your workers machines.
6.	Run Deployment.json playbook to deploy worker node container with kube-cluster.
7.	Run Copy.yml playbook to create deployment and pod and run the container.

Setup Requirements

Ansible should be installed on your machine.
