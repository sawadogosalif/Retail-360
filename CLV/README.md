# CLV : Customer Lifetime Value

"understanding and acting on customer lifetime value (CLV) is the most important part of your business’s sales efforts",AP. Fader and B. Hardie


Les clients traversent deux étapes dans leur « vie » avec une entreprise spécifique : ils sont « vivants » pour
une certaine période de temps, puis devenir définitivement inactif

## Prémière approche :Modélisation du Flux de transaction ("By till You Die")
#### Processus de transaction
+ Lorsqu'il est actif, un client achète "au hasard" autour de son taux de transaction moyen 
+ Les taux de transaction varient selon les clients (effet individuels inobservés)
<img src="https://latex.codecogs.com/svg.image?\lambda&space;exp^{-\lambda(t_j-t_{j-1})}&space;&space;&space;&space;&space;&space;&space;&space;" title="\lambda exp^{-\lambda(t_j-t_{j-1})} " />      , t_j> t_{j-1} >0

#### Processus d'abandon
+ Chaque client a une propension à l'abandon non observée qui varie selon les clients
+ La propension au churn (abondon) varie selon les clients
