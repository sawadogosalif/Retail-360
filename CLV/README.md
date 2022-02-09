# CLV : Customer Lifetime Value

"understanding and acting on customer lifetime value (CLV) is the most important part of your business’s sales efforts",AP. Fader and B. Hardie


Les clients traversent deux étapes dans leur « vie » avec une entreprise donnée :
1.  Ils sont « vivants » pour ne certaine période de temps, 
2.  Puis deviennent définitivement inactif

## Prémière approche :Modélisation du Flux de transaction (Le modèle Pareto/NBD )
#### Processus de transaction
##### Hypothèses 1
+ Lorsqu'il est actif, un client achète "au hasard" autour de son taux de transaction moyen 

De son vivant, le nombre de transactions effectuées par un client suit un processus de Poisson avec
taux de transaction λ ; donc la probabilité d'observer x transactions dans l'intervalle de temps
(0, t] est donné par :

<img src="https://latex.codecogs.com/svg.image?P(X(t)=x&space;|&space;\lambda)&space;=&space;&space;\frac{{\lambda&space;t&space;}^x&space;e^{&space;-\lambda&space;t}}{x!}" title="P(X(t)=x | \lambda) = \frac{{\lambda t }^x e^{ -\lambda t}}{x!}" />

Cela équivaut à supposer que le temps entre les transactions est distribué exponentiellement
avec taux de transaction λ

<img src="https://latex.codecogs.com/svg.image?f(t_j-t_{j-1}&space;|&space;\lambda&space;)=" title="f(t_j-t_{j-1} | \lambda )=" /> <img src="https://latex.codecogs.com/svg.image?\lambda&space;exp^{-\lambda(t_j-t_{j-1})}&space;&space;&space;&space;&space;&space;&space;&space;" title="\lambda exp^{-\lambda(t_j-t_{j-1})} " />      avec  <img src="https://latex.codecogs.com/svg.image?t_j>&space;t_{j-1}&space;>0" title="t_j> t_{j-1} >0" />

##### Hypothèses 2
+ Les taux de transaction varient selon les clients (effet individuels inobservés)

Ils suit une distribution gamma avec une forme paramètre r et paramètre d'échelle α 

<img src="https://latex.codecogs.com/svg.image?g(\lambda&space;|&space;r,&space;\alpha&space;)&space;=&space;\frac{\alpha&space;^{r}&space;\lambda^{r-1}&space;e^{-\alpha&space;\lambda}}{\Gamma&space;(r)&space;}&space;" title="g(\lambda | r, \alpha ) = \frac{\alpha ^{r} \lambda^{r-1} e^{-\alpha \lambda}}{\Gamma (r) } " />

#### Processus d'abandon
+ Chaque client a une propension à l'abandon non observée qui varie selon les clients

La "durée de vie" non observée d'un client de longueur τ (au-delà de laquelle il est considéré comme inactif)

est distribué de manière exponentielle avec un taux d'abandon μ :

<img src="https://latex.codecogs.com/svg.image?f(\tau&space;&space;|&space;\mu&space;)=&space;\mu&space;e^{-\mu&space;\tau}" title="f(\tau | \mu )= \mu e^{-\mu \tau}" />

+ La propension au churn (abondon) varie selon les clients
L'hétérogénéité des taux d'abandon parmi les clients suit une distribution gamma avec une forme
paramètre s et paramètre d'échelle β.

<img src="https://latex.codecogs.com/svg.image?g(\mu&space;|&space;s,&space;\beta&space;)&space;=&space;\frac{\beta&space;^{s}&space;\mu^{s-1}&space;e^{-\beta&space;\mu}}{\Gamma&space;(s)&space;}&space;" title="g(\mu | s, \beta ) = \frac{\beta ^{s} \mu^{s-1} e^{-\beta \mu}}{\Gamma (s) } " />


Les hypothèses 1 nous permettent de déduire que le distribution du nombre de transactions lorsque le client avant churn suit **une distribution binomiale négative** 

<img src="https://latex.codecogs.com/svg.image?P(X(t)&space;=&space;x&space;|&space;r,&space;\alpha)&space;=&space;&space;\int_{0}^{\infty&space;}&space;P(X(t)&space;=&space;x&space;|&space;\lambda)&space;&space;*&space;g(\lambda&space;|{r,&space;\alpha&space;)}&space;d&space;\lambda=\frac{\Gamma&space;(r&plus;x)}{\Gamma&space;(r)&space;x!}&space;{(\frac{\alpha&space;}{\alpha&space;&plus;t})}^r&space;&space;{(\frac{t&space;}{\alpha&space;&plus;t})}^x" title="P(X(t) = x | r, \alpha) = \int_{0}^{\infty } P(X(t) = x | \lambda) * g(\lambda |{r, \alpha )} d \lambda=\frac{\Gamma (r+x)}{\Gamma (r) x!} {(\frac{\alpha }{\alpha +t})}^r {(\frac{t }{\alpha +t})}^x" />


Les hypothèses 2 nous permettent de déduire que lA durée de vie du clients   est **une distribution de pareto** (Pareto distribution of the second kind)

<img src="https://latex.codecogs.com/svg.image?f(\tau&space;&space;|&space;s,&space;\beta)&space;=&space;&space;\int_{0}^{\infty&space;}&space;f(\tau&space;&space;|&space;\mu)&space;&space;*&space;g(\mu&space;|{s,&space;\beta&space;)}&space;d&space;\mu=\frac{s}{\beta}&space;{(\frac{\beta&space;}{\beta&space;&plus;\tau})}^{s&plus;1}" title="f(\tau | s, \beta) = \int_{0}^{\infty } f(\tau | \mu) * g(\mu |{s, \beta )} d \mu=\frac{s}{\beta} {(\frac{\beta }{\beta +\tau})}^{s+1}" />

#### Estimations

+ Supposons que nous sachions quand chacune des x transactions d'un client s'est produite pendant la période (0, T] ;
on note ces instants t1, t2,...,tx  (tx = Recency and x =Frequency).

On estime le modèle par maximum de vraissenblance en supposant que les 4 paramètres sont inconnus (sans condition sur λ and μ)

<img src="https://latex.codecogs.com/svg.image?L(\alpha&space;,&space;\beta&space;,&space;r,&space;&space;s|&space;x,&space;t_x,&space;T)=\int_{0}^{\infty&space;}\int_{0}^{\infty&space;}&space;L(\lambda&space;&space;,&space;\mu|&space;x,&space;t_x,&space;&space;T)&space;g(\lambda&space;|r,&space;\alpha&space;)&space;&space;g(\mu&space;|s,&space;\beta&space;)&space;d\lambda&space;d\mu&space;" title="L(\alpha , \beta , r, s| x, t_x, T)=\int_{0}^{\infty }\int_{0}^{\infty } L(\lambda , \mu| x, t_x, T) g(\lambda |r, \alpha ) g(\mu |s, \beta ) d\lambda d\mu " />

+ On peut calcul la moyenne et la variance du modèle pour chaque clients grace aux paramètres estimés :

<img src="https://latex.codecogs.com/svg.image?E(X(t)&space;|\alpha&space;,&space;\beta&space;,&space;r,&space;&space;s)=\int_{0}^{\infty&space;}\int_{0}^{\infty&space;}&space;E(X(t)|&space;\lambda&space;&space;,&space;\mu|)&space;g(\lambda&space;|r,&space;\alpha&space;)&space;&space;g(\mu&space;|s,&space;\beta&space;)&space;d\lambda&space;d\mu&space;" title="E(X(t) |\alpha , \beta , r, s)=\int_{0}^{\infty }\int_{0}^{\infty } E(X(t)| \lambda , \mu|) g(\lambda |r, \alpha ) g(\mu |s, \beta ) d\lambda d\mu " />


+ Calcul dela probabaibilité de survie grace à la distribution aposterio de λ and μ (Bayes)

+  On peut calculer l'espérence conditionenelle des achats :

Soit la variable aléatoire Y (t) le nombre d'achats effectués dans la période (T,T + t]. 
Nous sommes intéressé par le calcul de <img src="https://latex.codecogs.com/svg.image?E(Y&space;(t)|&space;x,&space;t_x,&space;T)" title="E(Y (t)| x, t_x, T)" />, le nombre d'achats attendus dans la période (T,T +t] pour un client avec historique d'achat (x, tx, T)
