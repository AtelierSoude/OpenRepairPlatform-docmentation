# Installation

!!! warning "Ce guide est réservée aux développeurs"
    Même si l'installation est simple, il est recommandé d'avoir quelques notions 

Il existe plusieurs façon de créer votre propre instance. Que ce soit en local sur votre machine ou sur un serveur distant, ce guide présente une **installation à réaliser sur Linux**. Une installation sur Mac OS X est similaire mais nécessite quelques adaptations. Une installation sur un système Windows n'a pas été testée. 

**Installation locale**
Pour une installation locale, installez l'application uniquement en mode développement [avec Docker Compose](#mode-developpement-docker) ou via [environnement virtuel](#mode-developpement-environnement-virtuel). 

**Installation sur un serveur distant**
En production, installez l'application uniquement en [mode production](#mode-production-docker).
Vous devez louer ou créer votre serveur Linux. Pour plus de simplicité, nous recommandons d'utiliser 
une instance Cloud. Par exemple chez [Scaleway](https://www.scaleway.com/fr/elements/). 
Accédez ensuite à votre serveur via [SSH](https://www.scaleway.com/en/docs/configure-new-ssh-key/). 


## Récupérer le dépôt
Si vous n'avez pas git
```
sudo apt install git
```

Puis
```
git clone https://github.com/AtelierSoude/OpenRepairPlatform.git
```
Entrez dans le dossier
```
cd OpenRepairPlatform
```


## Variables d'environnement 

Avant toute opération, Renseignez les variables Django, Postgres et Nginx dans `openrepairplatform/.env` 

```
POSTGRES_USER=CHANGE_ME 
POSTGRES_PASSWORD=CHANGE_ME
POSTGRES_DB_NAME=CHANGE_ME

DJANGO_SETTINGS_MODULE=openrepairplatform.settings.dev
SECRET_KEY=CHANGE_ME

EMAIL_PASSWORD=CHANGE_ME
EMAIL_HOST_USER=CHANGE_ME
EMAIL_HOST=CHANGE_ME

DOMAIN_NAME=CHANGE_ME
```

!!! danger "Attention"
    En mode développement sous environnement virtuel, les variables **POSTGRES_USER, POSTGRES_PASSWORD & DOMAIN_NAME** ne sont pas utilisées. Rendez-vous à la section [Mode développement : Environnement Virtuel ](#mode-developpement-environnement-virtuel) pour savoir pourquoi

Que signifie ces variables ?

**Variables POSTGRES**
```
POSTGRES_USER: Nom d'utilisateur de la base de donnée POSTGRES.
POSTGRES_PASSWORD: Mot de passe de l'utilisateur de la base de donnée POSTGRES.
POSTGRES_DB_NAME: Nom de la base de donnée POSTGRES. 

```

**Variables DJANGO**
```
DJANGO_SETTINGS_MODULE: openr.....settings.dev ou .prod
SECRET_KEY=CHANGE_ME: Renseignez une chaîne de caractère aléatoire 
```

**Variables d'e-mailing**

Des emails automatiques sont envoyés. Utilisez une adresse e-mail du type "no-reply@example.com"
```
EMAIL_PASSWORD: Le mot de passe de l'adresse email
EMAIL_HOST_USER: L'adresse mail 
EMAIL_HOST=CHANGE_ME: l'adresse IMAP utilisée 
```
**Variable NGINX**
```
DOMAIN_NAME: Le nom de votre domaine
```

Après avoir renseigné ces variables, vous pourrez lancer votre instance en mode production ou développement. 


## Mode production : Docker

Installez Docker 
```
sudo apt install docker
```

Lancer les scripts de démarrage (à la racine du dossier)
```
 ./deployment/clean.sh && ./deployment/build.sh && ./deployment/run.sh 
```

!!! warning "Nginx ne se lancera pas correctement"
    En effet, nginx va chercher un certificat SSL afin de sécuriser votre site. Celui-ci n'existe pas encore, il faut donc le créer.

Vous pouvez désormais naviguez sur le site via votre nom de domaine et passer au guide de premier lancement.

**Comment ajouter un certificat ?**

Suivez ce guide et télécharger vos fichiers *.pem, *.cert 

...


## Mode développement : Docker-compose 

C'est la voie la plus simple pour lancer l'application en locale. Cette installation s'accompagne d'un container Selenium. 

Installez Docker-compose 
```
sudo apt install docker-ce
```

Lancer cette commande
```
docker-compose up
```

!!! warning "Nginx ne se lancera pas correctement"
    En effet, nginx va chercher un certificat innexistant car vous n'avez pas à sécuriser votre site en locale. Pas de panique, ce n'est pas important. 

Vous pouvez désormais naviguez sur le site à l'adresse 127.0.0.1:8000 et passer au guide de premier lancement.

## Mode développement : Environnement Virtuel 

**Pré-requis**

Mettez à jour 
```
sudo apt update
```

Installez ces paquets 
```
sudo apt install python3-dev psycog2 python3-pip postgresql postgresql-contrib setuptools libxml2-dev
```

**POSTGRES**

Lancez postgres
```
postgres -d /usr/local/pgsql/data
```
Par défault, en développement, l'application tente de se connecter à POSTGRES en utilisant le compte de l'utilisateur courant et sans mot de passe. C'est pourquoi les variables d'environnements **POSTGRES_USER & POSTGRES_PASSWORD** ne sont pas utilisées. 

Créez la base de donnée (le même nom qu'entré dans le fichier .env)
```
createdb POSTGRES_DB_NAME
```

**Environnement virtuel et dépendances**
Installez virtualenv 
```
pip install --user virtualenv
```

Créez un environnement virtual (dans le dossier racine)
```
virtualenv venv
source bin/activate
```

Installez les dépendances PIP du projet 
```
pip install -r requirements_dev.txt 
```

**Lancement de l'application**

Premier lancement 
```
./manage.py migrate
./manage.py createsuperuser
./manage.py runserver
```
!!! info 
    Pour lancer l'application vous devez systématiquement activer votre environnement virtuel au préalable.

Ensuite, pour démarrer le service les prochaines fois (avec le serveur POSTGRES de lancé)
```
./manage.py runserver
```

Vous pouvez désormais naviguez sur le site à l'adresse 127.0.0.1:8000 et passer au guide de premier lancement.
