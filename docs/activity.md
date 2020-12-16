# Activité 

## Parcourir, découvrir

Depuis la page d’accueil, en cliquant sur l’icône ***Activités***, il est possible d’accéder à l’ensemble des activités, toutes organisations confondues, proposées au public. 
Ces dernières sont classées par catégories (Ateliers de réparations, ateliers de créations, formations, rencontres, ect…). Il est possible de voir par qui sont proposées ces activités mais aussi avoir une vue d’ensemble des différentes activités. En cliquant sur l’activité désirée, il est alors possible d’accéder au descriptif, plus précis et même de s’inscrire au prochain événement proposant l’activité en question.

### Page descriptive d’une activité

![Page descriptive de l'activité](../assets/activity/4.png)

Sur cette page on retrouve, l’image illustrant l’activité ; sa thématique, l’organisateur, sa description et ses prochains évènements dans la rubrique ***prochaines dates***. Pour participer à l’un des évènements, il suffit de cliquer sur l’encart de celui-ci et suivre les instructions de la rubrique [***Événements***](../event/reservation.md). Pour les administrateurs il est possible d’éditer et de supprimer sa propre activité.


## Créer une activité


!!! info "Qui peut créer une activité ?"
    Seul les administrateurs d'une organisation peuvent le faire. Voir [gestion des groupes]("organization/groups.md")

Il est indispensable de référencer une activité avant de créer un événement. 
Une activité est reliée à l'organisation qui la créée mais elle peut être utisée par d'autres.

### Accéder au formulaire 

**url** 
```
/<nom_organization>/controls/
```

Page «**Organisation**» → Choisir l'organisation → «**gérer**» → «**Ajouter une activité**»

![Création d'une activité](../assets/activity/1.png)

Pour la ***création d’une nouvelle activité*** : remplir les différents champs du formulaire.

### Formulaire 

| Champ | description |
|:--|:--|
|  ```activity type``` *(FR : type d’activité)* | ici donner un titre précis à l’activité (ex : Atelier de Réparation participative électronique » |
| ```category``` *(FR : catégorie)* | dans le menu défilant choisir le type d’activité (ex : formation). Champs non-obligatoire, mais conseillé pour le référencement des activités. |
| ```activity description``` *(FR : Description de l’activité)* | écrire une description précise de l’activité. Le texte peut être mise en forme via les différents outils proposés. Champ obligatoire à renseigner.|
| ```image``` | appuyer sur le bouton sur ***parcourir*** pour télécharger une image illustrant l’activité. Champ non-obligatoire mais conseillé pour l’identification des différentes activités. |

![Page de création](../assets/activity/2.png)

Pour finaliser, l’enregistrement de l’activité, cliquer sur le bouton vert ***valider***.
A présent, l’activité est créée et répertoriée dans la page générale ***activités***.

## Editer/Supprimer une activité

!!! info "Qui peut éditer/supprimer une activité ?"
    Seul les administrateurs de l'organisation créatrice de l'activité peuvent le faire. Voir [gestion des groupes]("organization/groups.md")

Pour modifier une activité, il faut se rendre sur le détail de l'activité. Un bouton d'édition et un bouton de suppression s'affichera si l'utilisateur à les droits. 
![Modifier](../assets/activity/5.png#center)

La suppression d'une activité ne supprimera pas les événements créés avec celle-ci. Mais ces événéments afficheront un type d'activité ***None*** . 

