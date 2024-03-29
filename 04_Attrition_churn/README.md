La première distinction pour les modèles de d'attrition est au niveau de la formalisation

1. un modèle supervisée de classification (classement) binaire pour estimer la probabilité qu'un client se désabonne à l'intérieur ou à l'horizon d'un certain point futur (par exemple, les 6 mois qui arrivent)

2. un modèle de type survie créant une estimation du risque d'attrition à chaque période (disons chaque mois pour l'année suivant)

Nous nous intéressons dans ce projet à réaliser le dernier type de modélisation:  ==> Utilisation des modèles de survie 


L'attrition des clients se produit lorsque les clients ou les abonnés cessent leur association avec une entreprise ou un service. Ce qui est un défi majeur dans les entreprises FMCG et retail car il est **cinq fois** moins cher de fidéliser un client existant que d'en acquérir un nouveau.


L’analyse statistique des durées de vie est un ensemble de méthodes et techniques
statistiques qui permettent de modéliser et d’estimer les lois décrivant le temps qui s’écoule
jusqu'à la survenue d’un événement particulier (qui n’est pas forcément la mort).

On notera par la suite T la durée de vie d’un individu (ou de
l’unité statistique en question). T est une variable aléatoire dont la fonction de répartition F a 

 La loi de la durée T est caractérisée entièrement par l’une de ces fonctions :
 
+ Sa fonction de densité : f(t) ;

+ Sa fonction de répartition : F(t) ;

+ Sa fonction de survie : <img src="https://latex.codecogs.com/svg.image?S(t)=&space;1-F(t)" title="S(t)= 1-F(t)" />

En plus de ces fonctions, il existe d’autres pouvant caractérisées T et possédant des
interprétations intéressantes dans l’analyse des durées de vie. Ces fonctions sont :

+ La fonction hasard (fonction de risque, taux de panne instantané ou taux de défaillance,
taux de sortie d’un état donné) : 
<img src="https://latex.codecogs.com/svg.image?h(t)=&space;\frac{F(t)}{1-F(t)}" title="h(t)= \frac{F(t)}{1-F(t)}" />


+ La fonction de risque cumulée est définie par H(t) 
<img src="https://latex.codecogs.com/svg.image?H(t)=&space;\int_{0}^{t}\lambda&space;(z)dz" title="H(t)= \int_{0}^{t}\lambda (z)dz" />
