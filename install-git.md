# INSTALACIÓN GIT

#### Creación de Script
##### Oficial Doc **[Git Install](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git/)**

## 2.- Instalación de Git - Centos
```console
yum install git -y
```
#### Comandos configuración Git para SSH
```console
git config --global user.name "Username"
git config --global user.email my-email@gmail.com
git branch -M main
git remote add origin git@github.com:<myorg>/>my-repo>.git
git remote -v
git push -u origin main
```
Configuración de merge
```sh
git config pull.rebase false  # merge
git config pull.rebase true   # rebase
git config pull.ff only       # fast-forward only
```
Visualizar los commits realizados
```sh
git log --oneline
git log --since="2023-04-22" --until="2023-04-23" --grep="ini" 
```

## 3. Configuración para especificación de key ssh
```sh
eval $(ssh-agent)
ssh-add ~/.ssh/2gcp
ssh-add -l
```
```console
256 SHA256:XXXXXXXXXXX cloud_user_p_1074bbd5@linuxacademygclabs.com (ED25519)
```
```sh
git clone ssh://cloud_user_p_1074bbd5@linuxacademygclabs.com@source.developers.google.com:2022/p/playground-s-11-ef434ec4/r/ACG-demo
```
```console
Cloning into 'ACG-demo'...
warning: You appear to have cloned an empty repository.
```
Remover llave agregada
```sh
ssh-add -d ~/.ssh/2gcp
```
```console
Identity removed: /Users/miguelangelvilahuallpa/.ssh/2gcp ED25519 (cloud_user_p_1074bbd5@linuxacademygclabs.com)
```
