# Voir / modifier un objet


## Détail d'un objet
```
inventory/<stuff_id>
```
Le détail d'un objet est visible par tout utilisateur, même non connecté. 
Si le-la propriétaire est un-e utilisateur-rice dont le profil n'est pas visible, son nom sera caché des utilisateurs-rices qui ne font pas partie d'une des organisations, dont il-elle fait partie. 

Sur cette page, sont visibles toutes les données relatives à cet objet, ses dossiers de réparations, et un historique afin de visualiser le suivi de cet objet.

![stuff-detail](../assets/stuff/stuff-detail.png#center)


## Modifier un objet

Sur la page de détail d'un objet, il est possible d'éditer les différentes informations de celui-ci. 

Chaque champ utilise des formulaires séparés qui s'affichent en cliquant sur le bouton :fa-pencil:

!!! info "Qui peut éditer un objet ?"
    L'utilisateur-rice propriétaire, les volontaires, les actifs-ves et les administrateurs-rices des organisations dont le-la propriétaire est membre. Si le-la propriétaire est une organisation, ses membres peuvent également l'éditer.
    
**Modifier le type d'appareil et les informations**

En cliquant sur le bouton d'édition vert à côté du nom de l'objet, un formulaire analogue au[formulaire de création d'objet](inventory.md#formulaire) apparaît. Il est possible d'y modifier les informations de l'objet ainsi que son type d'appareil.

![stuff-information](../assets/stuff/stuff-info.png#small)


**Transférer la propriété**

Un champ autocomplétif permet de choisir soit un-e utilisateur-rice, soit une organisation. Il est également possible de désigner un-e utilisateur-rice non connu-e comme nouveau-elle propriétaire. 

!!! danger 
    Si vous transférez la propriété à une personne qui n'est pas membre de vos organisations, ou à un-e utilisateur-rice inconnu de l'application, vous n'aurez plus aucun droit de modification sur cet objet. 

![stuff-owner](../assets/stuff/stuff-owner.png#small)


**Modifier la visibilité**

Une case à cocher permet de rendre visible ou non cet objet. Si la case est cochée, il sera visible dans [l'inventaire global](inventory.md#inventaire-globale). 

![stuff-visibility](../assets/stuff/stuff-visibility.png#small)


**Modifier la localisation**

Un champ autocomplétif propose les différents [lieux](../location.md) de l'application. Si le-la propriétaire est un-e utilisateur-rice, par défaut l'objet n'est pas localisé. 

Il est possible de supprimer la localisation de l'objet en cliquant sur la croix rouge. 

![stuff-place](../assets/stuff/stuff-place.png#small)

**Modifier l'état** 

Une liste déroulante propose de modifier l'état de l'objet. 

![stuff-visibility](../assets/stuff/stuff-state.png#small)

**Créer/modifier des dossiers de réparations** 

Voir la [section relative aux réparations](repair.md). 
