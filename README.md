	Execute the file using command 
I have written in yaml file
Kubectl apply -f springmongo.yml






Setup Kubernetes Cluster
1.	Create 2  machines
2.	I have mentioned ubuntu commands here
System Requirements
Master Machine: 4 GB RAM, 2 Core Processer
Worker Machines: 1 GB RAM, 1 Core Processer
2. Execute below commands in both master and slave machines.
sudo apt-get update-y
sudo apt-get install -y apt-transport-https
sudo su-
curl-s https://packages.cloud.google.com/apt/doc/apt-key.gpg I apt-key add-


cat <<EOF >/etc/apt/sources.list.d/kubernetes.list
deb https://apt.kubernetes.io/ kubernetes-xenial main
EOF


apt-get update -y
swapoff -a

apt install docker.io -y
usermod-aG docker ubuntu
systemctl restart docker
systemctl enable docker.service
apt-get install -y kubelet kubeadm kubectl kubernetes-cni
systemctl daemon-reload
systemctl start kubelet
systemctl enable kubelet.service

These things are only for master
3. Execute below Commands only in master machine.
==In Master Node Start=-=
#Execute below command as root user
kubeadm init
#exit root user & execute as normal user

pert cACheg peratng ysles. Operating syslem
3. Execute below commands only in master machine.
===In Master Node Start======== ==============
#Execute below command as root user
kubeadm init
#exit root user & execute as normal user
mkdir -p $HOME/.kube
sudo cp-i /etc/kubernetes/admin.conf $HOME/.kube/config
kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=S(kubectl version
base64 | tr-d n)
kubectl get nodes
kubectl get pods--all-namespaces


This is for worker node
copy kubeadm join token and execute in Worker Nodes to join to cluster
Setup Jenkins Server to deploy applications into Kubernetes Cluster
We can deploy docker applications into Kubernetes cluster from Jenkins








