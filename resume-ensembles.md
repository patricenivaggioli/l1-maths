# Fiche de cours — Les ensembles (L1 informatique)

Un **ensemble** est une collection d’éléments distincts, sans ordre. Par exemple, $\{1,2,3\}=\{3,2,1,2\}$. On écrit $x\in A$ si $x$ appartient à $A$, et $x\notin A$ sinon. L’ensemble vide, noté $\varnothing$, ne contient aucun élément.

## Inclusion et égalité

$A\subseteq B$ signifie que **tout élément de $A$ appartient à $B$**. En particulier, $\varnothing\subseteq A$ et $A\subseteq A$.

Pour prouver que $A=B$, on montre les deux inclusions : $A\subseteq B$ et $B\subseteq A$. Attention à distinguer $x\in A$ (appartenance) de $A\subseteq B$ (inclusion). Ainsi, $\varnothing\neq\{\varnothing\}$ : le second ensemble contient un élément.

## Opérations principales

Avec $A=\{1,2,3\}$ et $B=\{3,4\}$ :

| Opération | Définition | Résultat |
|---|---|---|
| $A\cup B$ | Éléments présents dans $A$ **ou** $B$ | $\{1,2,3,4\}$ |
| $A\cap B$ | Éléments présents dans $A$ **et** $B$ | $\{3\}$ |
| $A\setminus B$ | Éléments de $A$ absents de $B$ | $\{1,2\}$ |
| $A\triangle B$ | Éléments présents dans un seul des deux ensembles | $\{1,2,4\}$ |

Deux ensembles sont **disjoints** si leur intersection est vide. Si l’on fixe un ensemble de référence $U$, le complémentaire de $A$ est $A^c=U\setminus A$.

## Lois à connaître

L’union et l’intersection sont commutatives et associatives. L’intersection se distribue sur l’union, et réciproquement. Les **lois de De Morgan** sont particulièrement utiles :

$$
(A\cup B)^c=A^c\cap B^c
\qquad\text{et}\qquad
(A\cap B)^c=A^c\cup B^c.
$$

Elles traduisent le fait que « ni dans $A$ ni dans $B$ » équivaut à « hors de $A$ et hors de $B$ ».

## Ensembles construits à partir d’autres ensembles

- L’**ensemble des parties** $\mathcal P(A)$ contient tous les sous-ensembles de $A$. Si $A=\{a,b\}$, alors $\mathcal P(A)=\{\varnothing,\{a\},\{b\},\{a,b\}\}$.
- Le **produit cartésien** $A\times B$ contient les couples $(a,b)$ tels que $a\in A$ et $b\in B$. Ici, l’ordre du couple compte : $(a,b)$ peut différer de $(b,a)$.

Pour des ensembles finis, en notant $|A|$ le nombre d’éléments de $A$ :

$$
|\mathcal P(A)|=2^{|A|},\qquad
|A\times B|=|A||B|,\qquad
|A\cup B|=|A|+|B|-|A\cap B|.
$$

## Raisonnement et lien avec l’informatique

On peut définir un ensemble par une propriété : $\{x\in\mathbb N\mid x\text{ est pair}\}$. Pour établir une inclusion $A\subseteq B$, on choisit un élément quelconque $x\in A$, puis on prouve que $x\in B$. Cette méthode sert notamment à démontrer l’égalité de deux résultats de requêtes ou de deux collections de données.

**À retenir :** les ensembles décrivent *quels* éléments sont présents ; les produits cartésiens décrivent des couples ; les opérations d’union, d’intersection et de complémentaire correspondent aux connecteurs logiques « ou », « et » et « non ».
