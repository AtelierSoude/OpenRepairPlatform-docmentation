# Voir / modifier un objet


## Détail d'un objet
```
inventory/<stuff_id>
```
Le détail d'un objet est visible par tout utilisateur, même non connecté. 
Si le propriétaire est un utilisateur dont le profil n'est pas visible, son nom sera caché des utilisateurs qui ne font pas parti d'une de ses organisations. 

Sur ce page, toutes les données relatives à cet objet, ainsi que ses dossiers de réparations sont visibles. Un historique afin de visualiser le suivi de cet objet.

![stuff-detail](../assets/stuff/stuff-detail.png#center)


## Modifier un objet

Sur la page de détail d'un objet, il est possible d'éditer les différentes informations de celui-ci. 

Chaque champ utilise des formulaires séparés qui s'affichent en cliquant sur le bouton :fa-pencil:

!!! info "qui peut éditer un objet ?"
    L'utilisateur propriétaire, les volontaires, actifs et administrateurs des organisations dont le propriétaire est membre. Si le propriétaire est une organisation, ces sont égalements ces membres-ci qui peuvent l'éditer. 
    
**Modifier le type d'appareil et les informations**

En cliquant sur le bouton d'édition vert qui se situe proche du nom de l'objet, un formulaire proche du [formulaire de création d'objet](inventory.md#formulaire) apparaît. Il est possible d'y modifier les informations de l'objet ainsi que son type d'appareil.

![stuff-information](../assets/stuff/stuff-info.png#small)


**Transférer la propriété**

Un champ d'autocomplétion permet de choisir soit un utilisateur, soit une organisation. Il est également possible de désigner un utilisateur non connnu comme nouveau propriétaire. 

!!! danger 
    Si vous transférez la propriété à une personne qui n'est pas membre de vos organisations, ou à un utilisateur inconnu de l'application, vous n'aurez plus aucuns droits de modifications sur cet objet. 

![stuff-owner](../assets/stuff/stuff-owner.png#small)


**Modifier la visibilité**

Une case à cocher permet de rendre visible ou non cet objet. Si la case est cochée, il sera visible dans [l'inventaire global](inventory.md#inventaire-globale). 

![stuff-visibility](../assets/stuff/stuff-visibility.png#small)


**Modifier la localisation**

Un champ d'autocomplétion propose les différentes [lieux](../location.md) de l'application. Si le proporiétaire est un utilisateur, par défaut l'objet n'est pas localisé. 

Il est possible de ne pas localiser l'objet en supprimant la valeur en cliquant sur la croix rouge. 

![stuff-place](../assets/stuff/stuff-place.png#small)

**Modifier l'état** 

Une liste déroulante propose de modifier l'état de l'objet. 

![stuff-visibility](../assets/stuff/stuff-state.png#small)

**Créer/modifier des dossiers de réparations** 

Voir la [section relative aux réparations](repair.md). 
