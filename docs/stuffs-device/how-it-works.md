# Comment ça marche

L'application propose l'inventaire et le suivi de réparation d'objet. Cette fonctionnalité utilise plusieurs entités différentes :

- [Catégories](#categorie)
- [Appareils](#appareil)
- [Objets](#objet)
- [Dossiers de réparations](#dossier-de-reparation)
- [Interventions](#intervention)

Les objets sont stockés dans des [inventaires](inventory.md#inventaires). 
Un objet est un exemplaire d'un appareil Cet appareil possède une catégorie. 
Cet objet peut posséder des dossiers de réparations et chaque dossier peut contenir plusieurs interventions. 

**Exemple**
>l'utilisateur possède un objet dans son inventaire. Cet objet est exemplaire d'un appareil dénommé cafeterie Krups MKRE43. Cet appareil est issu de la catégorie cafetière à capsule. Cette catégorie descend de la catégorie cafetière et petit électroménager. Cet objet possède un dossier ouvert le 14/01/2024. Ce dossier contient une intervention réalisée le 14/01/2024. 

![schema-inventory](/assets/schema-inventory.jpg#small)

## Catégorie

Les catégories d'appareils ont une dénonation (ex. Ordinatateur portable). Chaque catégories peut être une catégorie enfant d'une autre. 
> Informatique > ordinateur > ordinateur portable 

## Appareil

Un appareil, ou autrement dit *un produit*, est une entité à part entière. C'est une entité non physique.

| Champ | Description |
|:--|:--|
| ```Categorie``` | Catégorie de l'appareil |
| ```Marque``` | Marque de l'appareil - liste prédéfinie |
| ```Modèle``` | Modèle ou désignation de l'appareil - champ libre |
| ```Description``` | Champ HTML. ex : descriptions techniques |
| ```Image``` | Une photo de l'appareil |
| ```liens``` | Liste de liens relatifs. ex : schéma techniques, tutoriels |

## Objet

Un objet est un exemplaire d'un appareil. L'objet est une entité phyisique possèdée et invetoriée. L'objet est possédé par un utilisateur ou une organisation. 

| Champ | Description |
|:--|:--|
| ```Appareil``` | L'appareil dont il est l'exemplaire |
| ```Propriétaire``` | Un utilisateur ou une organisation |
| ```Etat``` | Etat de l'appareil (fonctionnel, incomplet/partiel, réparé, en panne, désassemblé, évaporé) |
| ```Information``` | Champ HTML. Différentes informations à son propos |
| ```Localisation``` | Si l'objet est localisé dans un lieu référencé sur l'application |
| ```Subpart``` | Si l'objet est inclu dans un autre objet |
| ```Visibilité``` | Visible ou non dans [l'inventaire global](inventory.md#inventaire-global) |


## Dossier de réparation 

Un objet possède un ou des dossiers de réparations. Un dossier est donc lié à un objet.

| Champ | Description |
|:--|:--|
| ```Objet``` | L'objet lié |
| ```En cours``` | Dossier en cours ou terminé |
| ```Date``` | Date de l'ouverture du dossier |

Ces dossiers peuvent inclure plusieurs interventions. 
Il peut exister plusieurs interventions car une réparation peut s'étendre sur plusieurs séances et peut nécessiter plusieurs actions. 

## Intervention

Une intervention est reliée à un dossier de réparation. 

Elle est relative à une date d'execution ou à un événement. Elle contient une série d'actions (observation, raisonnement, action, status).  

| Champ | Description |
|:--|:--|
| ```Observation``` | L'observation désigne l'état innitial de l'objet. Ce que l'utilisateur a observé. Ex: « ne chauffe plus » .  |
| ```Raisonnement``` | Le raisonnement désigne le cheminement  de la reflexion, le diagnostic. |
| ```Action``` | L'action désigne ce qui a été fait, essayé. Ex: « changement de la resistance ».  |
| ```Status``` | Le status désigne l'état de l'objet suite à cette action. Ex: « chauffe », ou « ne chauffe toujours pas » . |

Ces actions sont des entités à part entières dans la base de données et sont notamment disponibles via un champ d'autocomplétion. Il est donc nécessaire de choisir parmi des termes déjà utilisés. Il également est possible de créer ces termes. La formulation de ces actions est restreinte à quelques mots qui évoquent le plus clairement possible l'action. 

## Normalisation des données 

La séparation en plusieurs entités de ce qu'*est un objet* permet de minimalement normer les données créées. En effet, une fois une entité créée, elle est réutilisable. Les doublons sont évités, les formulations peut évocatrices limités. 

Ainsi, il sera possible de catégoriser, trier et rechercher des réparations par type d'appareil ou par actions. 