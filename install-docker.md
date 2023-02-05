# INSTALACIÓN DOCKER

#### Creación de Script
##### Oficial Doc **[Docker Install](https://docs.docker.com/engine/install/centos/)**

## 1.- Instalación de Docker - Centos

```console 
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