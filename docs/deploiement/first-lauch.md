# Premier lancement

!!! info 
    Ce guide s'utilise après l'[installation](/deploiement/installation.md) de l'application.

## Accéder 
Une fois l'application installée et lancée, elle est disponible en locale via l'URL suivante :

```
127.0.0.1:8000
```

S'il s'agit d'une installation sur serveur distant, c'est l'URL de votre domaine. 

## Administrer 

Rendez-vous à l'URL suivante : 

```
/admin
```


C'est ici que vous administrez le site. 

Connectez-vous en tant qu'administrateur-rice en utilisant le compte créé par défaut :

```
mail : admin@example.com
```

```
mot de passe : adminpass
```

!!! Danger "Attention"
    Modifiez le mot de passe de cet utilisateur-administrateur en utilisant un mot de passe fort. C'est important !

Pour plus d'informations sur l'administration consultez la documentation de Django. 

## Initialiser

L'application est vide de toute donnée dans sa base. 
Pour commencer à utiliser l'application, il est nécessaire de faire quelques actions préalables.

**Renseignez des catégories d'activités**

En utilisant l'URL suivante: 
```
admin/event/activitycategory/
```

Indiquez des catégories générales. 

Pour comprendre de quoi il s'agit, voir la page concernant les [activités](../activity.md).

**Renseignez des catégories d'appareils** 

En utilisant l'URL suivante:
```
admin/inventory/category/
```

Ces catégories sont utilisées pour créer des appareils. 

Pour comprendre de quoi il s'agit, voir la page concernant les [catégories d'appareils](../stuffs-device/how-it-works.md#categorie)

Vous pouvez créer vos propres catégories. Néanmoins un jeu initial de données est disponible.
Le jeu de données ```electronics_categories_FR.json``` est présent à la racine du dossier ***Inventory*** du dépôt. Voir [Importer / exporter des données](#importer-exporter-des-donnees)

Il n'y a plus rien d'autre à faire ici, il n'est plus nécessaire d'utiliser l'administration du site. 

**Créez une organisation**

Vous pouvez [créer la première organisation](../organization/create.md) de l'application via l'interface utilisateur. 

Lorsque vous créez cette organisation, vous devenez automatiquement administrateur de celle-ci. Vous avez désormais tous les droits pour effectuer les actions possibles sur cette application lorsque votre êtes administrateurs de l'application et d'une organisation. 

**Modifiez votre profil**

Ultime étape. Modifiez votre profil en suivant ce [guide](../account/profil.md) avec vos réelles informations.


## Personnaliser 

**Nom du site**
Pour modifier le nom de l'application, modifiez la variable du processeur de contexte. Modifier "Réparons" par le nom de votre application.

```
openrepairplatform/context-processors.py 
```

```
def site_title(request):
   return {'site_title':'Réparons'} 
```

**Logo**

Pour mettre le logo adéquat à votre site, il suffit de remplacer les fichiers correspondants par les vôtres. 

Les logos sont contenus dans ce dossier :
```
openrepairplatform/static/img 
```

Remplacez le fichier *logo.png* par le vôtre (il s'agit du logo visible dans le menu).
Remplacez le fichier *logo-simple.png* par le vôtre (il s'agit du logo visible sur la page de connexion).

Ensuite, rendez-vous sur le site ```https://www.favicon-generator.org/``` pour créer vos *favicons*. 
Remplacer tous les fichiers inclus dans le dossier ```openrepairplatform/static/img/favicon``` par vos fichiers de favicons. 

**Schéma de couleurs**

Pour personnaliser le schéma des couleurs de votre site, modifiez les variables SASS du fichier : 
```
/openrepairplatform/static/scss/variables.scss
```

!!! info 
    La personnalisation des couleurs n'est pas encore complètement implémentées. Utilisez des codes couleurs de luminosités proches du set prédéfini. 


## Importer / exporter des données 

Importer des données peut être utile si vous possédez, par exemple, déjà une base de donnée de membres de votre ancien site/organisation.

Lorsque vous cliquez sur certaines entités de la base de données, les options ***importer*** ou ***exporter*** sont disponibles dans l'interface, en haut à droite.

!!! danger "Importer des données demande de solides connaissances."
    Pour importer des données, vous devez créer un fichier .json ou .csv respectant strictement la structure des données de l'application. 
    Pour connaître la structure des données que vous souhaitez importer, il vous faut parcourir les modèles de données du code de l'application. 

