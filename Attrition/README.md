La première distinction pour les modèles de d'attrition est au niveau de la formalisation

1. un modèle supervisée de classification (classement) binaire pour estimer la probabilité qu'un client se désabonne à l'intérieur ou à l'horizon d'un certain point futur (par exemple, les 6 mois qui arrivent)

2. un modèle de type survie créant une estimation du risque d'attrition à chaque période (disons chaque mois pour l'année suivant)

Nous nous intéressons dans ce projet à réaliser le dernier type de modélisation:  ==> Utilisation des modèles de survie 


L'attrition des clients se produit lorsque les clients ou les abonnés cessent leur association avec une entreprise ou un service.
Il existe de nombreux modèles pour prédire si un client va se désabonner ou non. Le problème ne s'arrête pas là, les entreprises doivent déployer certaines stratégies pour fidéliser les clients qui sont au bord du désabonnement car il est **cinq fois** moins cher de fidéliser un client existant que d'en acquérir un nouveau. Les modèles statistiques peuvent être utilisés pour dériver et évaluer des stratégies personnalisées, ce qui est un défi majeur dans les entreprises FMCG et retail.


L’analyse statistique des durées de vie est un ensemble de méthodes et techniques
statistiques qui permettent de modéliser et d’estimer les lois décrivant le temps qui s’écoule
jusqu'à la survenue d’un événement particulier (qui n’est pas forcément la mort).

On notera par la suite T la durée de vie d’un individu (ou de
l’unité statistique en question). T est une variable aléatoire dont la fonction de répartition F a 

 La loi de la durée T est caractérisée entièrement par l’une de ces fonctions :
###. Sa fonction de densité : f(t) ;

###. Sa fonction de répartition : F(t) ;

###Sa fonction de survie : S(t) = 1-F(t).

En plus de ces fonctions, il existe d’autres pouvant caractérisées T et possédant des
interprétations intéressantes dans l’analyse des durées de vie. Ces fonctions sont :

4. La fonction hasard (fonction de risque, taux de panne instantané ou taux de défaillance,
taux de sortie d’un état donné) : h(t)=F(t)/1-F(t)
