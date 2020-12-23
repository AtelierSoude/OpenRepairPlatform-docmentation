# Installation

!!! warning "Ce guide est réservé aux développeurs-euses"
    Même si l'installation est simple, il est recommandé d'avoir quelques notions de programmation.

Il existe plusieurs façons de créer votre propre instance. Que ce soit en local sur votre machine ou sur un serveur distant, ce guide présente une **installation à réaliser sur Linux**. Une installation sur Mac OS X est similaire mais nécessite quelques adaptations. Une installation sur un système Windows n'a pas été testée. 

**Installation locale** :
Pour une installation locale, installez l'application uniquement via [environnement virtuel](#mode-developpement-environnement-virtuel). 

**Installation sur un serveur distant** :
En production, installez l'application uniquement en [mode production](#mode-production-docker-compose).
Vous devez louer ou créer votre serveur Linux. Pour plus de simplicité, nous recommandons d'utiliser 
une instance Cloud. Par exemple chez [Scaleway](https://www.scaleway.com/fr/elements/). 
Accédez ensuite à votre serveur via [SSH](https://www.scaleway.com/en/docs/configure-new-ssh-key/). 


## Récupérer le dépôt
Si vous n'avez pas *Git*
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

Avant toute opération, renseignez les variables Django, Postgres et Nginx dans `openrepairplatform/.env` 

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

Que signifient ces variables ?

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


## Mode production : Docker-compose

Installez Docker-compose
```
sudo apt install docker-compose
```

Se placer dans le dossier deployment
```
 cd deployment
```
Lancer le l'application avec docker-compose :

```
docker-compose up -d
```

Si vous *lancer* l'application pour la *première fois*, il vous faudra générer un *certificat* https *let'sencrypt*, afin de protéger les utilisateurs se connectant à votre site, au moyen du script situé ci-dessous (situé également dans le dossier deployment). Il génèra un certificat https en résolvant un challenge décrit par le protocole [acme](https://en.wikipedia.org/wiki/Automated_Certificate_Management_Environment). Il faut pour cela que vous ayez *configurer* au préalable votre *DNS* pour que le nom de domaine que vous ayez choisi (ex mon_super_atelier.fr) pointe sur l'adresse ip de votre machine, veillez à configurer une *entrée DNS ipv4 et ipv6*. Pour résoudre ce challenge, le *port 80* de votre machine doit être *exposé*. Il peut être bloquer par le firewall de votre machine et/ou d'un équipement réseau local (ex routeur), bien penser à autoriser le trafique ipv4 et ipv6. Il faudra veiller également à ouvrir le *port 443* pour permttre aux utilisateurs de se connecter à votre plateforme. 

```
./init-letsencrypt.sh
```

Toutes les données de l'application sont situées dans `./deployment/openrepairplatform_data`. Vous pouvez changer cela en éditant le fichier `./deployment/docker-compose.yml` 

Vous pouvez désormais naviguez sur le site via votre nom de domaine et passer au guide de premier lancement.

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
Par défaut, en développement, l'application tente de se connecter à POSTGRES en utilisant le compte de l'utilisateur courant et sans mot de passe. C'est pourquoi les variables d'environnements **POSTGRES_USER & POSTGRES_PASSWORD** ne sont pas utilisées. 

Créez la base de données (le même nom que celui entré dans le fichier .env)
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

Ensuite, pour démarrer le service les prochaines fois (avec le serveur POSTGRES lancé)
```
./manage.py runserver
```

Vous pouvez désormais naviguer sur le site à l'adresse 127.0.0.1:8000 et passer au guide de premier lancement.
