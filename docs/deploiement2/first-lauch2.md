# Premier lancement

!!! info 
    Ce guide est réservé à l'après [installation](/deploiement/installation.md) de l'application

## Accéder 
Une fois l'application installée et lancée, elle est disponible en locale via l'URL suivante :

```
127.0.0.1:8000
```

S'il s'agit d'une installation sur serveur distant, c'est l'URL de votre domaine. 

## Administrer 

Rendez-vous l'URL suivante : 

```
/admin
```


C'est ici que vous administrez le site. 

Connectez-vous en tant qu'administrateur en utilisant le compte créé par défaut :

```
mail : admin@example.com
```

```
mot de passe : adminpass
```

!!! Danger "Attention"
    Modifiez le mot de passe de cet utilisateur administrateur en utilisant un mot de passe fort. C'est important !

Pour plus d'informations sur l'administration consultez la documentation de Django. 

## Innitialiser

L'application est vide de toute données dans sa base. 
Pour commencer à utiliser l'application, il faut faire quelques actions.

**Renseignez des catégories d'activités**

En utilisant l'URL suivante: 
```
admin/event/activitycategory/
```

Indiquez des catégories générales. 

Pour comprendre de quoi il s'agit, voir la page qui concerne les [activités](activity.md)

**Renseignez des catégories d'appareils** 

En utilisant l'URL suivante:
```
admin/inventory/category/
```

Ces catégories sont utilisées pour créer des appareils. 

Pour comprendre de quoi il s'agit, voir la page qui concerne les [catégories d'appareils](/inventory/device.md)

Vous pouvez créer vos propres catégories. Néanmois un jeu de données initial est disponible.
Ce jeu de données est présent à la racine du dossier *Inventory* du dépôt. 

Il n'y a plus rien d'autre à faire ici, il n'est plus nécessaire d'utiliser l'administration du site. 

**Créez une organisation**

Vous pouvez [créer la première organisation](/organization/create.md) de l'application via l'interface utilisateur. 

Lorsque vous crééz cette organisation, vous devenez automatiquement administrateur de celle-ci. Vous avez désormais tous les droits pour effectuer les actions possibles sur cette application lorsque votre êtes administrateurs de l'application et d'une organisation. 

**Modifiez votre profil**

Ultime étape. Modifiez votre profil en suivant ce [guide](account/profile.md) avec vos rééele informations.


## Personnaliser 

**Nom du site**
Blabla

**Logo**

Pour mettre le logo adéquat à votre site, il suffit de remplacer le fichier "" par le votre. 
Ensuite, rendez-vous sur le site "" pour créer vos favicon. Remplacer tous les fichiers inclus dans "" par vos fichiers de favicons. 

**schéma de couleurs**

Pour personnaliser le schéma des couleurs de votre site, modifier les variables SASS du fichier : 
```
/openrepairplatform/static/scss/variables.scss
```

!!! info 
    La personnalisation des couleurs n'est pas encore complètement implémentées. Utilisez des codes couleurs de luminosités proches du set prédéfini. 


## Importer / exporter des données 

Importer des données peut être utile si vous posséder, par exemple, déjà une base de donnée de membres de votre ancien site/organisation.

Lorsque vous cliquez sur chaque entité de la base de données, les options *importer* ou *exporter* sont disponibles dans l'intercae. 

!!! danger "Importer des données demande de solides connaissances."
    Pour importer des données, vous devez créer un fichier .csv respectant strictement la structure des données de l'application. 
    Pour connaître la structure des données que vous souhaitez importez, il vous faut parcourir les modèles de données du code de l'application. 

