L’analyse statistique des durées de vie est un ensemble de méthodes et techniques
statistiques qui permettent de modéliser et d’estimer les lois décrivant le temps qui s’écoule
jusqu'à la survenue d’un événement particulier (qui n’est pas forcément la mort)
Les données de durées de vie sont des données positives qu’on représentera par des
variables aléatoires $`\sqrt{2}`$
. On notera par la suite T la durée de vie d’un individu (ou de
l’unité statistique en question). T est une variable aléatoire dont la fonction de répartition F a 
4
pour support IR+
. Cela limite à priori la classe des modèles paramétriques utilisables dans
l’analyse des durées de vie, mais on pourra toujours transporter une variable aléatoire sur IR+
à l’aide d’une transformation convenable. En pratique cette variable représente la durée passé
dans un état donné (chômage, célibataire) et/ou celle séparant deux événements (changement
de compagne d‘assurance, changement d’emploi, …).
 La loi de la durée T est caractérisée entièrement par l’une de ces fonctions :
 Sa fonction de densité : f(t) ;
 Sa fonction de répartition : F(t) ;
 Sa fonction de survie : S(t) = 1-F(t).
En plus de ces fonctions, il existe d’autres pouvant caractérisées T et possédant des
interprétations intéressantes dans l’analyse des durées de vie. Ces fonctions sont :
 La fonction hasard (fonction de risque, taux de panne instantané ou taux de défaillance,
taux de sortie d’un état donné) :
( )
( )
( )
S t
f t
h t  ; 
© 2022 GitHub, Inc.
Terms
Privac
