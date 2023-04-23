# INSTALACIÓN GIT

#### Creación de Script
##### Oficial Doc **[Git Install](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git/)**

## 2.- Instalación de Git - Centos
```console
# yum install git -y
```
#### Comandos configuración Git para SSH
```console
# git config --global user.name "Username"
# git config --global user.email my-email@gmail.com
# git branch -M main
# git remote add origin git@github.com:<myorg>/>my-repo>.git
# git push -u origin main
```
## 3. Configuración para especificación de key ssh
```sh
ssh-add ~/.ssh/tu-archivo-ssh
ssh-add -l
```
```console
256 SHA256:77Q0gM9YZMyDesTAdkeuYboCpbyhBnY51laEDQhAbjA cloud_user_p_1074bbd5@linuxacademygclabs.com (ED25519)
```
```sh
git clone ssh://cloud_user_p_1074bbd5@linuxacademygclabs.com@source.developers.google.com:2022/p/playground-s-11-ef434ec4/r/ACG-demo
```
```console
Cloning into 'ACG-demo'...
warning: You appear to have cloned an empty repository.
```