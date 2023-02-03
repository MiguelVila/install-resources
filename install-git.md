# INSTALACIÓN DE SERVICIOS Y BINARIOS

## 1.- Instalación de Docker
##### Creación de Script
```console
# sudo su 
# cat <<EOF > install_docker.sh
yum install -y yum-utils
yum-config-manager \
--add-repo \
https://download.docker.com/linux/centos/docker-ce.repo
yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
systemctl enable --now docker
EOF
```
##### Ejecución de Script
```console
# sh install_docker.sh
```


## 2.- Instalación de Git
```console
# yum install git -y
```