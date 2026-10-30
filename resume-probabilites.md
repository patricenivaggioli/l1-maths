# Fiche de cours — Probabilités (L1 informatique)

Une **expérience aléatoire** a plusieurs résultats possibles. L’ensemble de ces résultats est l’**univers** $\Omega$ ; un **événement** est une partie de $\Omega$. Pour un dé équilibré, $\Omega=\{1,2,3,4,5,6\}$ et $A=\{2,4,6\}$ est l’événement « obtenir un nombre pair ».

## Calculer la probabilité d’un événement

Une probabilité vérifie $0\leq P(A)\leq1$, $P(\Omega)=1$ et $P(\varnothing)=0$. Si tous les résultats sont équiprobables :

$$
P(A)=\frac{|A|}{|\Omega|}.
$$

Les règles essentielles sont :

$$
P(A^c)=1-P(A),\qquad
P(A\cup B)=P(A)+P(B)-P(A\cap B).
$$

Si $A$ et $B$ sont **incompatibles**, alors $A\cap B=\varnothing$ et leurs probabilités s’additionnent.

## Conditionnement et indépendance

La probabilité de $A$ *sachant* $B$, lorsque $P(B)>0$, est :

$$
P(A\mid B)=\frac{P(A\cap B)}{P(B)}.
$$

Ainsi, $P(A\cap B)=P(B)P(A\mid B)$. Deux événements sont **indépendants** si $P(A\cap B)=P(A)P(B)$. Attention : *indépendants* ne signifie pas *incompatibles*.

La formule de **Bayes** permet d’inverser un conditionnement :

$$
P(A\mid B)=\frac{P(B\mid A)P(A)}{P(B)}.
$$

## Variables aléatoires discrètes

Une variable aléatoire $X$ associe un nombre à chaque résultat. Sa **loi** donne les probabilités $P(X=x)$, dont la somme vaut $1$. Son espérance et sa variance sont :

$$
E(X)=\sum_x xP(X=x),\qquad
V(X)=E(X^2)-E(X)^2.
$$

L’espérance représente la moyenne obtenue à long terme ; la variance mesure la dispersion autour de cette moyenne. Pour $n$ essais indépendants ayant chacun une probabilité de succès $p$, le nombre de succès suit une **loi binomiale** :

$$
P(X=k)=\binom nk p^k(1-p)^{n-k},\qquad E(X)=np.
$$

**Méthode à retenir :** définir l’univers et les événements, vérifier si les résultats sont équiprobables, puis choisir la formule adaptée. En informatique, ces outils servent notamment à analyser les algorithmes aléatoires et les erreurs de transmission.
