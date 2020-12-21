# Activité 

## Parcourir, découvrir

Depuis la page d’accueil, en cliquant sur l’icône ***Activités***, il est possible d’accéder à l’ensemble des activités, toutes organisations confondues, proposées au public. 
Ces dernières sont classées par catégories (ateliers de réparation, ateliers de création, formations, rencontres, ect.). Il est possible de voir par quelle organisation sont proposées ces activités mais aussi d'avoir une vue d’ensemble des différentes activités. En cliquant sur l’activité désirée, il est alors possible d’accéder au descriptif, plus précis et même de s’inscrire au prochain événement proposant l’activité en question.

### Page descriptive d’une activité

![Page descriptive de l'activité](../assets/activity/activity-page.png)

Sur cette page on retrouve l’image illustrant l’activité, sa thématique, l’organisation, sa description et ses prochains évènements dans la rubrique ***prochaines dates***. Pour participer à l’un des évènements, il suffit de cliquer sur l’encart de celui-ci et suivre les instructions de la rubrique [***Événements***](event/reservation.md). 


## Créer une activité


!!! info "Qui peut créer une activité ?"
    Seul-e-s les administrateurs-rices d'une organisation peuvent le faire. Voir [gestion des groupes](organization/groups.md)

Il est indispensable de référencer une activité avant de créer un événement. 
Une activité est reliée à l'organisation qui la crée mais elle peut être utilisée par d'autres.

### Accéder au formulaire 

**url** 
```
/<nom_organization>/controls/
```

Page ***Organisation*** → ***Choisir l'organisation*** → ***Gérer*** → ***Ajouter une activité***

![Création d'une activité](../assets/activity/org-manage-activity.png)

Pour la ***création d’une nouvelle activité*** : remplir les différents champs du formulaire.

### Formulaire 

| Champ | Description |
|:--|:--|
|  ```activity type``` *(FR : type d’activité)* | Ici donner un titre précis à l’activité (ex : Atelier de Réparation participative électronique » |
| ```category``` *(FR : catégorie)* | Dans le menu défilant choisir le type d’activité (ex : formation). Champ facultatif, mais conseillé pour le référencement des activités. |
| ```activity description``` *(FR : Description de l’activité)* | Ecrire une description précise de l’activité. Le texte peut être mis en forme via les différents outils proposés. Champ obligatoire.|
| ```image``` | Appuyer sur le bouton  ***Parcourir*** pour télécharger une image illustrant l’activité. Champ falcultatif mais conseillé pour l’identification des différentes activités. |

![Page de création](../assets/activity/activity-form.png)

Pour finaliser l’enregistrement de l’activité, cliquer sur le bouton vert ***Valider***.
A présent, l’activité est créée et répertoriée dans la page générale ***Activités***.

## Editer/Supprimer une activité

!!! info "Qui peut éditer/supprimer une activité ?"
    Seul-e-s les administrateurs-rices de l'organisation créatrice de l'activité peuvent le faire. Voir [gestion des groupes]("organization/groups.md")

Pour modifier une activité, il faut se rendre sur le détail de l'activité. Un bouton d'édition et un bouton de suppression s'affichera si l'utilisateur-rice a les droits. 

![Modifier](../assets/activity/activity-button.png#center)

La suppression d'une activité ne supprimera pas les événements créés avec celle-ci. Mais ces événéments afficheront un type d'activité ***None*** . 

