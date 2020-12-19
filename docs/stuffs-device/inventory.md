# Inventorier

## Ajouter un objet 

Les champs et les entités utilisés par ce forumulaire sont décrits [ici](how-it-works.md). 

![stuff-create](../assets/stuff/stuff-create.png#small)


### Formulaire 

**Ce formulaire comportent plusieurs étapes:** 

1. Choisir la [catégorie](how-it-works.md#categorie) de l'objet à créer grâce à la liste d'autocomplétion déroulante.
2. Choisir le [type d'appareil](how-it-works.md#appareil). Les appareils déjà créés s'afficheront dans la liste liste d'autocomplétion déroulante. Les choix s'affichent conditionnellement au regard du choix de la catégorie précédemment réalisé. 
3. Si l'appareil recherché n'existe pas, il est possible de le créer en cochant la case ***je ne trouve pas l'appareil dans la liste***. L'utilisateur est invité à renseigner les [champs relatifs à un appareil](how-it-works.md#appareil)
4. Ensuite les [champs relatifs à l'objet s'affichent](how-it-works#objet) apparaissent
5. En cochant la case ***je souhaite rajouté un dossier de réparation***, le [formulaire de création de dossier de réparation](repair.md) s'affiche ici et il est possible de créer un dossier ainsi qu'une [intervention innitiale](repair.md) directement à la création de l'objet. 

### Soumettre le formulaire

A la soumission du formulaire, suivant les choix réalisés, un [objet](how-it-works.md#objet), un [appareil](how-it-works.md#appareil) et un [dossier de réparation](how-it-works.md#dossier-de-reparation) avec une [intervention](how-it-works.md#intervention) innitiale seront créés. 

Il est possible de créer un objet sur 3 pages différentes. 
Ces pages utilisent ce même formulaire, qui agit différemment suivant où il est utilisé.

- [inventaire utilisateur](#inventaires)
    * L'utilisateur sera automatiquement propriétaire de l'objet 
- [inventaire organisation](#inventaire-organisation)
    * L'organisation sera automatiquement propriétaire de l'objet 
    * Le champ localisation s'affichera 
- [à la confirmation de réservation](#indiquer-l-objet-que-l-on-souhaite-reparer)
    * L'utilisateur sera automatiquement propriétaire de l'objet 
    * Il n'est possible de renseigner seulement une observation à la création du dossier de réparation dans ce formulaire

## Inventaires 

Les objets ainsi créés seront visibles dans un inventaire. 
Il existe plusieurs inventaires différents. 

### Inventaire utilisateur
Chaque utilisateur possède un inventaire d'objet. Cet inventaire est visible sur son profil.
Il est possible d'ajouter un objet à cet inventaire en utlisant le bouton **ajouter un objet à l'inventaire**.

!!! info "qui peut ajouter un objet ?"
    L'utilisateur en question peut lui même effectuer cette action, ainsi que les volontaires, actifs et administrateurs des organisations dont l'utilisateur est membre.

### Inventaire organisation 
De la même façon, une organisation peut gérer son inventaire (ou stock) et ajouter des objets.

Le tableau qui liste les objets permet de filtrer, ordonner et de choisir les différentes données affichées.

!!! info "qui peut ajouter un objet ?"
    Less volontaires, actifs et administrateurs de l'organisation.

### Inventaire global 
Cette page recence les objets dont la propriété « is_visible » est activée. Cette page est visible de tout utilisateur, connecté ou non.
Elle présente donc les objets qui sont disponibles, par exemple, à la vente ou au don.



