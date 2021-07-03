# LAMP on Debian 64Bits

Ce playbook installera un environnement LAMP sécurisé (Linux, Apache, MySQL et PHP) sur une machine Debian 64 Bits.


## Paramètres

- `mysql_root_password`: Mot de passe du compte racine MySQL.
- `app_user`: Utilisateur non root distant sur l'hôte Ansible qui sera propriétaire des fichiers d'application.
- `group`: Groupe utilisateur qui sera propriétaire des fichiers d'application.
- `http_host`: Nom de domaine.
- `http_conf`: Nom du fichier de configuration qui sera créé dans Apache.
- `http_port`: Port HTTP, la valeur par défaut est 80.
- `https_port`:Port HTTPS, la valeur par défaut est 443.

## Fonctionnement du Playbook

### 1. Obtention du Playbook
```shell
git clone https://github.com/BOURGUITSamuel/Ansible-Playbook-LAMP
cd Ansible-Playbook-LAMP/
```

### 2. Personnalisation des options

```shell
nano vars/default.yml
```

```yml
---
mysql_root_password: "mysql_root_password"
app_user: "your_app_user"
group: "your user group"
http_host: "your_domain"
http_conf: "your_domain.conf"
http_port: 80
https_port: 443
disable_default: true

```

### 3. Lancement du Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] playbook.yml
``