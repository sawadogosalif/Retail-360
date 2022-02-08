# CLV : Customer Lifetime Value

"understanding and acting on customer lifetime value (CLV) is the most important part of your business’s sales efforts",AP. Fader and B. Hardie


Les clients traversent deux étapes dans leur « vie » avec une entreprise spécifique : ils sont « vivants » pour
une certaine période de temps, puis devenir définitivement inactif

## Prémière approche :Modélisation du Flux de transaction ("By till You Die")
#### Processus de transaction
+ Lorsqu'il est actif, un client achète "au hasard" autour de son taux de transaction moyen 
+ Les taux de transaction varient selon les clients (effet individuels inobservés)

De son vivant, le nombre de transactions effectuées par un client suit un processus de Poisson avec
taux de transaction λ ; donc la probabilité d'observer x transactions dans l'intervalle de temps
(0, t] est donné par :<img src="https://latex.codecogs.com/svg.image?P(X(t)=x&space;|&space;\lambda)&space;=&space;&space;\frac{{\lambda&space;t&space;}^x&space;e^{&space;-\lambda&space;t}}{x!}" title="P(X(t)=x | \lambda) = \frac{{\lambda t }^x e^{ -\lambda t}}{x!}" />

Cela équivaut à supposer que le temps entre les transactions est distribué exponentiellement
avec taux de transaction λ

<img src="https://latex.codecogs.com/svg.image?f(t_j-t_{j-1}&space;|&space;\lambda&space;)=" title="f(t_j-t_{j-1} | \lambda )=" /> <img src="https://latex.codecogs.com/svg.image?\lambda&space;exp^{-\lambda(t_j-t_{j-1})}&space;&space;&space;&space;&space;&space;&space;&space;" title="\lambda exp^{-\lambda(t_j-t_{j-1})} " />      avec  <img src="https://latex.codecogs.com/svg.image?t_j>&space;t_{j-1}&space;>0" title="t_j> t_{j-1} >0" />

#### Processus d'abandon
+ Chaque client a une propension à l'abandon non observée qui varie selon les clients

La "durée de vie" non observée d'un client de longueur τ (au-delà de laquelle il est considéré comme inactif)
est distribué de manière exponentielle avec un taux d'abandon μ : <img src="https://latex.codecogs.com/svg.image?f(\tau&space;&space;|&space;\mu&space;)=&space;\mu&space;e^{-\mu&space;\tau}" title="f(\tau | \mu )= \mu e^{-\mu \tau}" />

+ La propension au churn (abondon) varie selon les clients
