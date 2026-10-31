# Fiche de cours — Les ensembles (L1 informatique)

Un **ensemble** est une collection d’éléments distincts, sans ordre. Par exemple, $\lbrace 1,2,3\rbrace=\lbrace 3,2,1,2\rbrace$. On écrit $x\in A$ si $x$ appartient à $A$, et $x\notin A$ sinon. L’ensemble vide, noté $\varnothing$, ne contient aucun élément.

On peut **construire un ensemble par compréhension** en appliquant une expression à chaque valeur autorisée. Par exemple :

$$
\lbrace 2x+1\mid x\in\lbrace 1,2\rbrace\rbrace
=\lbrace 2\cdot1+1,\,2\cdot2+1\rbrace
=\lbrace 3,5\rbrace.
$$

Le symbole $\mid$ se lit « tel que » ; on peut aussi écrire un point-virgule à sa place.

## Inclusion et égalité

$A\subseteq B$ signifie que **tout élément de $A$ appartient à $B$**. En particulier, $\varnothing\subseteq A$ et $A\subseteq A$.

Pour prouver que $A=B$, on montre les deux inclusions : $A\subseteq B$ et $B\subseteq A$. Attention à distinguer $x\in A$ (appartenance) de $A\subseteq B$ (inclusion). Ainsi, $\varnothing\neq\lbrace \varnothing\rbrace$ : le second ensemble contient un élément.

## Opérations principales

Avec $A=\lbrace 1,2,3\rbrace$ et $B=\lbrace 3,4\rbrace$ :

| Opération | Définition | Résultat |
|---|---|---|
| $A\cup B$ | Éléments présents dans $A$ **ou** $B$ | $\lbrace 1,2,3,4\rbrace$ |
| $A\cap B$ | Éléments présents dans $A$ **et** $B$ | $\lbrace 3\rbrace$ |
| $A\setminus B$ | Éléments de $A$ absents de $B$ | $\lbrace 1,2\rbrace$ |
| $A\triangle B$ | Éléments présents dans un seul des deux ensembles | $\lbrace 1,2,4\rbrace$ |

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

- L’**ensemble des parties** $\mathcal P(A)$ contient tous les sous-ensembles de $A$. Si $A=\lbrace a,b\rbrace$, alors $\mathcal P(A)=\lbrace \varnothing,\lbrace a\rbrace,\lbrace b\rbrace,\lbrace a,b\rbrace\rbrace$.
- Le **produit cartésien** $A\times B$ contient les couples $(a,b)$ tels que $a\in A$ et $b\in B$. Ici, l’ordre du couple compte : $(a,b)$ peut différer de $(b,a)$.

Pour comprendre pourquoi $|\mathcal P(A)|=2^{|A|}$, supposons $A=\lbrace a_1,\ldots,a_n\rbrace$. Chaque sous-ensemble correspond à un mot de $n$ bits : le bit $i$ vaut **1** si $a_i$ est présent, **0** sinon. Chaque bit a deux valeurs possibles, donc il existe $2\times\cdots\times2=2^n$ sous-ensembles. Par exemple, pour $A=\lbrace a,b,c\rbrace$, le mot `101` représente $\lbrace a,c\rbrace$ ; les $2^3=8$ mots binaires représentent les huit parties de $A$.

Pour des ensembles finis, en notant $|A|$ le nombre d’éléments de $A$ :

$$
|\mathcal P(A)|=2^{|A|},\qquad
|A\times B|=|A||B|,\qquad
|A\cup B|=|A|+|B|-|A\cap B|.
$$

## Raisonnement et lien avec l’informatique

On peut définir un ensemble par une propriété : $\lbrace x\in\mathbb N\mid x\text{ est pair}\rbrace$. Pour établir une inclusion $A\subseteq B$, on choisit un élément quelconque $x\in A$, puis on prouve que $x\in B$. Cette méthode sert notamment à démontrer l’égalité de deux résultats de requêtes ou de deux collections de données.

**À retenir :** les ensembles décrivent *quels* éléments sont présents ; les produits cartésiens décrivent des couples ; les opérations d’union, d’intersection et de complémentaire correspondent aux connecteurs logiques « ou », « et » et « non ».
