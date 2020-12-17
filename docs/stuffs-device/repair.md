# Dossiers de réparation 

Un objet possède un ou des dossiers de réparations. Un dossier (RepairFolder) est donc lié à un objet (Stuff). Le dossier est en cours ou clos/terminé (ongoing). Il possède une date de création (open_date), par défaut la date du jour. 
Ces dossiers peuvent inclure plusieurs interventions. Il peut exister plusieurs interventions car une réparation peut s'étendre sur plusieurs séances et il est ainsi possible de suivre les actions effectuées. 

# Interventions

Une intervention est reliée à un dossier de réparation (folder). Elle est relative à une date d'execution ou à un événement. Elle contient une série d'actions (observation, reasoning, action, status).  
L'observation désigne l'état innitial de l'objet. Ce que l'utilisateur a observé. Par exemple « ne chauffe plus » . Le raisonnement désigne le cheminement  de la reflexion, le diagnostic. 
L'action désigne ce qui a été fait, essayé. Par exemple : « changement de la resistance ». 
Le status désigne l'état de l'objet suite à cette action. Par exemple « chauffe », ou « ne chauffe toujours pas » . 
Observation, Reasoning, action et status sont des  à part entière.
