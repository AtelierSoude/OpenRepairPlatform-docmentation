# Comment ça marche

L'application propose l'inventaire et le suivi de réparation d'objet. Cette fonctionnalité utilise plusieurs entités différentes :

- [Catégories](#categorie)
- [Appareils](#appareil)
- [Objets](#objet)
- [Dossiers de réparations](#dossier-de-reparation)
- [Interventions](#intervention)

Un objet est un exemplaire d'un appareil Cet appareil possède une catégorie. 
Cet objet peut posséder des dossiers de réparations et chaque dossier peut contenir plusieurs interventions. 

**Exemple**
>l'utilisateur possède un objet dans son inventaire. Cet objet est exemplaire d'un appareil dénommé cafeterie Krups MKRE43. Cet appareil est issu de la catégorie cafetière à capsule. Cette catégorie descend de la catégorie cafetière et petit électroménager. Cet objet possède un dossier ouvert le 14/01/2024. Ce dossier contient une intervention réalisée le 14/01/2024. 

![schema-inventory](/assets/schema-inventory.jpg)

## Catégorie



## Appareil

Un appareil (Device) possède une catégorie (category). Cette catégorie peut être l'enfant d'une autre. (ex : informatique > ordinateur > ordinateur portable). La marque (brand) est également un modèle de données à part entière (ex : Apple). Le champ description est libre et peut inclure des informations complémentaire sur ce type d'appareil (ex : renseignements techniques etc.). Le champ model est un champ texte libre qui permet de renseigner la désignation de l'appareil en question, le modèle ou sa référence (ex : Macbook A1286).


## Objet

Un objet est un exemplaire d'un appareil (Device). L'objet est possédé par un utilisateur (member_owner) ou une organisation (organization_owner). Un champ information permet d'écrire librement des détails sur cet objet en particulier. Il peut être faire parti d'un autre objet (subpart). Il peut être localisé dans un lieu identifié (place). Cela est notamment utile si l'objet est disposible dans les locaux de l'organisation et si un membre a déposé son objet entre deux ateliers de réparation par exemple.  Un objet possède un état (state) qui peut être : fonctionnel, réparé, fonctionement partiel, en panne, démantelé, évaporé. 
 Le champ is_visible permet de déclarer l'objet comme visible du publique dans la page générale « Stock ». 


# Dossier de réparation 

Un objet possède un ou des dossiers de réparations. Un dossier (RepairFolder) est donc lié à un objet (Stuff). Le dossier est en cours ou clos/terminé (ongoing). Il possède une date de création (open_date), par défaut la date du jour. 
Ces dossiers peuvent inclure plusieurs interventions. Il peut exister plusieurs interventions car une réparation peut s'étendre sur plusieurs séances et il est ainsi possible de suivre les actions effectuées. 

# Interventions

Une intervention est reliée à un dossier de réparation (folder). Elle est relative à une date d'execution ou à un événement. Elle contient une série d'actions (observation, reasoning, action, status).  
L'observation désigne l'état innitial de l'objet. Ce que l'utilisateur a observé. Par exemple « ne chauffe plus » . Le raisonnement désigne le cheminement  de la reflexion, le diagnostic. 
L'action désigne ce qui a été fait, essayé. Par exemple : « changement de la resistance ». 
Le status désigne l'état de l'objet suite à cette action. Par exemple « chauffe », ou « ne chauffe toujours pas » . 
Observation, Reasoning, action et status sont des  à part entière.
