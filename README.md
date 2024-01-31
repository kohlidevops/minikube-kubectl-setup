# To Setup Minikube and access the kubernetes using kubectl

### Pre-req

1. Ubuntu 22 machine with t3.medium (2 vCPU & 2 RAM)
2. 20 GB storage

### To install minikube on machine

Launch ubuntu22 with t3.medium instance and SSH to machine

You can refer this doc

```
https://minikube.sigs.k8s.io/docs/start/
```

Install docker

```
sudo apt-get update -y
sudo apt-get upgrade -y
sudo apt-get install docker.io -y
sudo usermod -aG docker ubuntu
sudo chmod 777 /var/run/docker.sock
newgrp docker
sudo systemctl restart docker
```

Install minikube

```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
minikube start --driver=docker
```

![image](https://github.com/kohlidevops/minikube-kubectl-setup/assets/100069489/74bbce53-f90f-49c2-98bd-6de438f166f0)


### To install kubectl on machine

you can refer this doc

```
https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
```

I'm going to Install using native package management

```
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.29/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.29/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubectl
kubectl cluster-info
```

![image](https://github.com/kohlidevops/minikube-kubectl-setup/assets/100069489/fd40cbba-c0a7-4e4a-9fd8-4978f744dd9f)

