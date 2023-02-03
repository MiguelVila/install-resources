# INSTALACIÓN DE SERVICIOS Y BINARIOS

## Instalación de Docker
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
#### Ejecución de Script
```console
# sh install_docker.sh
```


### Into container 
```console
# docker exec -ti python /bin/sh
# python diagram-file.py
```