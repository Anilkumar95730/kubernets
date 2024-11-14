# kubernetes
It is also container management tool or container orchistration tool

it is basically like a cluster

              cluster : it is a group of node and server
              > master node
              > workernode
IT is an open-source container orchestration platform.

It is used to automates many of the manual processes like deploying, managing, and scaling containerized applications.

Kubernetes was developed by GOOGLE using GO Language. Google donated K8's to CNCF in 2014.

1st version was released in 2015.

# why KUBERNETES:
   Containers are a good and easy way to bundle and run your applications. In a production environment, you need to manage the containers that run the applications and ensure that there is no downtime. In docker we used docker swarm for this. but any how docker has drawbacks!

so we moved to KUBERNETES.

# Architecture:
![image](https://github.com/user-attachments/assets/5cea0150-c614-4620-ae63-6d08b203c2b8)

# cluster:
It is a group of servers It will have both manager and worker nodes.

Master Node is used to assign tasks to Worker Nodes.

Worker node will perform the task.

we have 4 components in Master Node

1.API Server

2.ETCD

3. Controllers-manager
  
4. Schedulers

we have 3 components in Worker Node.

1.	Kubelet
	
2.	Kube-Proxy
	
3.container runtime

# 1.API Server :

                   It is for all the communication purpose .It revecive the request and send the request to user

# 2. Schedulers :
                
                   It is for the scheduling of ports in kubernetes and it will receive the data from the API server and create the port and schedule it

# ETCD : 
                  it will store the data of kubernets of(master nodes and worker nodes)

# Controllers-manager :
                 It will verify the container creation
                 It is used to perform the operations which is scheduled by the scheduler.
                 it wil control the containers creation in worker nodes.

# Controllers-manager : they are two types 
        1.cloud controller : is a kubernetes control plane component that embeds cloud specific control logic
        2.controller manager : is a de=aemon that monitors the state of kubernetes cluster and changes to keep the application running

# kubelet:  

       it always look for the  pod is running or not.it will inform to API server if it not works

# kubeProxy:

           It is used to maintain a network connection between worker and manager nodes.


# Pod:
     A group of one or more containers.

# container:

It is a virtual machine which does not have any OS. it is used to run the applications in worker nodes.

# kubernetes cluster setup  :

        There are multiple ways to setup kubernetes cluster.

        1.	SELF MANAGER K8'S CLUSTER
        a.mini kube (single node cluster) 
        b.kubeadm(multi node cluster)
        c. KOPS

        2.	CLOUD MANAGED K8'S CLUSTER
        a.	AWS EKS
        b.	AZURE AKS
        c.	GCP GKS
        d.	IBM IKE

# MINIKUBE:

It is a tool used to setup single node cluster on K8's.
It contains API Servers, ETDC database and container runtime It helps you to containerized applications.
It is used for development, testing, and experimentation purposes on local.
Here Master and worker runs on same machine It is a platform Independent.
By default it will create one node only.
Installing Minikube is simple compared to other tools. NOTE: But we dont implement this in real-time

# MINIKUBE SETUP:

         REQUIREMENTS:
         2 CPUs or more
         2GB of free memory 
         20GB of free disk space 
         Internet connection
         Container or virtual machine manager, such as: Docker.


UPDATE SERVER:	

      1	apt update -y
      2	apt upgrade -y
     
INSTALL DOCKER: 

       3	sudo apt install curl wget apt-transport-https -y
       4	sudo curl -fsSL https://get.docker.com -o get-docker.sh sh get-docker.sudo h
       
INSTALL MINIKUBE:	

        5	sudo curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
        6	sudo mv minikube-linux-amd64 /usr/local/bin/minikube
        7	sudo chmod +x /usr/local/bin/minikube
        8	sudo minikube version
        
INSTALL KUBECTL: 

      9	sudo curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
      10	sudo curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
      11	sudo echo "$(cat kubectl.sha256) kubectl" | sha256sum --check
      12	sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
      13	sudo kubectl version --client
      14	sudo kubectl version --client --output=yaml
      15	sudo minikube start --driver=docker --force

# KUBECTL:

kubectl is the CLI which is used to interact with a Kubernetes cluster.

We can create, manage pods, services, deployments, and other resources We can also monitoring, troubleshooting, scaling and updating the pods.

To perform these tasks it communicates with the Kubernetes API server.

It has many options and commands, to work on.

The configuration of kubectl is in the $HOME/.kube directory. 

The latest version is 1.27
