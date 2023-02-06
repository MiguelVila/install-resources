# INSTALACIÓN KUBERNETES

#### Creación de Script

## 1.- Deshabilitación de servicios
```sh 
cat <<EOF > disable-svc.sh
systemctl stop firewalld.service
systemctl disable firewalld.service
setenforce 0
sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/sysconfig/selinux
sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config
sed -i '/ swap / s/^\(.*\)$/#\1/g' /etc/fstab
swapoff -a
EOF
```

```sh
sh disable-svc.sh
```
## 2.- Habilitación de iptables
```sh 
cat <<EOF >  /etc/sysctl.d/k8s.conf
net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
EOF

sysctl --system
```
## 3.- Instalación Docker  

```sh 
cat <<EOF > install_docker.sh
yum install -y yum-utils
yum-config-manager \
--add-repo \
https://download.docker.com/linux/centos/docker-ce.repo
yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
systemctl enable --now docker
EOF

sh install_docker.sh
```

## 4.- Instalación Kubernetes
```sh
cat <<EOF > /etc/yum.repos.d/kubernetes.repo
[kubernetes]
name=Kubernetes
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
enabled=1
gpgcheck=0
repo_gpgcheck=0
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
EOF

yum install -y kubelet-1.21.0-0.x86_64 kubeadm-1.21.0-0.x86_64 kubectl-1.21.0-0.x86_64  
systemctl enable kubelet && systemctl start kubelet
```
