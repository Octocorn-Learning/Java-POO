# TP 1

Vous trouverez ci-dessous différents exercices purement algorithmiques.

Ils ont pour objectif de vous familiariser avec la syntaxe Java, et les bases de la programmation.

Vous créerez un dépot github pour ce TP, et vous y ajouterez vos différents exercices.
Vous utiliserez la classe `Main` pour tester vos différents exercices et réaliserez une classe par exercice,
dans un package `tp1.exerciceX` (où X est le numéro de l'exercice).

- Pour tous les exercices, vous gérerez également les exceptions.
- Par souci de facilité d'utilisation, préférez les méthodes statiques.

> Vous réaliserez un commit par exercice !  
> Si l'exercice peut être réalisé de plusieurs manières, vous réaliserez un commit par version.

---

## Exercice 1 : Calculer la moyenne 📖

Écrivez un programme qui demande à l'utilisateur de saisir 3 notes, puis qui affiche la moyenne de ces notes.

### Contraintes 🚨

- Les notes saisies doivent être des nombres entiers.
- Les notes saisies doivent être comprises entre 0 et 20.
- La moyenne doit être un nombre entier.
- La fonction doit prendre en paramètre un tableau de notes.

### Exemples 🔦

#### Exemple 1

- Note 1 saisie : `10`
- Note 2 saisie : `10`
- Note 3 saisie : `10`
- Moyenne : `10`

#### Exemple 2

- Note 1 saisie : `15`
- Note 2 saisie : `10`
- Note 3 saisie : `5`
- Moyenne : `10`

---

## Exercice 2 : Calculer le prix TTC 📖

Écrivez un programme qui demande à l'utilisateur de saisir un prix HT, puis qui affiche le prix TTC correspondant.
Le prix TTC est calculé en ajoutant la TVA au prix HT. La TVA est de 20%.

### Contraintes 🚨

- Votre fonction prendra en paramètre un nombre float.
- Le prix HT saisi doit être un nombre positif.
- Le prx TTC est un nombre positif float.

### Exemples  🔦

#### Exemple 1

- Prix HT saisi : `100`
- Prix TTC : `120`
- Explication : `100 * 1.2 = 120`

#### Exemple 2

- Prix HT saisi : `50`
- Prix TTC : `60`
- Explication : `50 * 1.2 = 60`

---

## Exercice 3 : Nombre Palindrome 📖

Un palindrome est un nombre qui peut se lire de la même manière de gauche à droite et de droite à gauche.

> 121 est un palindrome

Écrivez un programme qui permet de déterminer si un nombre saisi par l'utilisateur est un palindrome.

### Contraintes 🚨

- Votre programme retournera `true` si le nombre est un palindrome, `false` sinon.
- Vous n'avez pas le droit de convertir le nombre en `String`.
- Le nombre doit être supérieur à 0.
- Le nombre doit contenir au moins 2 chiffres

### Exemples de résultats attendus 🔦

#### Exemple 1

- Nombre saisi : `121`
- Résultat : `true`
- Explication : `121` est un palindrome

#### Exemple 2

- Nombre saisi : `123`
- Résultat : `false`
- Explication : `123` n'est pas un palindrome

---

## Exercice 4 : Contient un doublon ? 📖

Écrivez un programme qui permet de déterminer si un tableau d'entiers contient un doublon.

### Contraintes 🚨

- Votre programme retournera `true` si le tableau contient un doublon, `false` sinon.

### Exemples de résultats attendus 🔦

#### Exemple 1

- Tableau saisi : `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`
- Résultat : `false`
- Explication : Le tableau ne contient pas de doublon

#### Exemple 2

- Tableau saisi : `[1, 2, 3, 4, 5, 6, 7, 8, 9, 1]`
- Résultat : `true`
- Explication : Le tableau contient un doublon avec `1`

### Indices 💡

- Il y a au moins 3 approches possibles : 
    - Utiliser une boucle dans une boucle 
    - Trier le tableau
    - Utiliser un HashMap

### Aller plus loin 💪

Si vous le souhaitez, vous pouvez essayer de mettre en place les 3 solutions !

---

## Exercice 5 : Nombre romain vers nombre arabe 📖

Écrivez un programme qui permet de calculer la valeur d'un nombre romain saisi par l'utilisateur.

Les valeurs des chiffres romains sont les suivantes :

| Chiffre romain | Valeur |
|----------------|--------|
| I              | 1      |
| V              | 5      |
| X              | 10     |
| L              | 50     |
| C              | 100    |
| D              | 500    |
| M              | 1000   |

- `I` peut être placé avant `V` et `X` pour faire 4 ou 9.
- `X` peut être placé avant `L` et `C` pour faire 40 ou 90.
- `C` peut être placé avant `D` et `M` pour faire 400 ou 900.

### Contraintes 🚨

- L'input ne peut contenir que des chiffres romains.
- Les chiffres romains ne peuvent aller que de 1 à 3999.
- La longueur de l'input ne peut excéder 15 caractères.
- L'input doit contenir au moins un chiffre romain.

### Exemples de résultats attendus 🔦

#### Exemple 1

- Nombre saisi : `X`
- Résultat : `10`
- Explication : `X` vaut `10`

#### Exemple 2

- Nombre saisi : `LVIII`
- Résultat : `58`
- Explication : `L` = `50`, `V` = `5`, `III` = `3`

#### Exemple 3

- Nombre saisi : `MCMXCII`
- Résultat : `1992`
- Explication : `M` = `1000`, `CM` = `900`, `XC` = `90`, `II` = `2`

### Indices 💡

2 méthodes :
- Imbriquer des `if` et des `else if` pour chaque cas particulier.
- Utiliser un `HashMap`

### Aller plus loin 💪

- Essayez de réaliser les deux méthodes !

---

## Exercice 6 : Element majorité 📖

Écrivez un programme qui permet d'indiquer le nombre majoritaire dans un tableau d'entiers.
Partez du principe qu'il y a forcément au moins un élément majoritaire.

> ❗Comme pour élire un président de la république, il faut avoir plus de 50% des voix pour être élu !


### Contraintes 🚨

- Votre programme retournera l'élément le plus présent dans le tableau.
- La fonction prendra en paramètre un tableau d'entiers.
- Le tableau peut comprendre des nombres entre -10^9 et 5 * 10^4.
- La longueur du tableau peut aller de 1 à 50000.

### Exemples de résultats attendus 🔦

#### Exemple 1

- Tableau saisi : `[3, 2, 3]`
- Résultat : `3`
- Explication : Chaque élément n'est présent qu'une seule fois. 1 est le premier élément trouvé.

#### Exemple 2

- Tableau saisi : `[2, 2, 1, 1, 1, 2, 2]`
- Résultat : `1`
- Explication : 1 est le seul à être présent deux fois.

#### Exemple 3

- Tableau saisi : `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`
- Résultat : `5`
- Explication : Il n'y a pas d'élément majoritaire, mais 5 est l'élément du milieu

#### Exemple 4

- Tableau saisi : `[1, 1, 1, 2, 2, 3, 4, 5, 5]`
- Résultat : `2`
- Explication : Il n'y a pas d'élément majoritaire ici, l'input est donc mauvais !

### Indices 💡

Il y a au moins 2 manières de résoudre cet exercice :
- Trier le tableau
- Utiliser un HashMap

### Aller plus loin 💪

- Essayez d'utiliser les 2 méthodes !

#### BONUS : Méthode Boyer-Moore

Essayez de résoudre ce problème avec l'algorithme de [Boyer-Moore](https://en.wikipedia.org/wiki/Boyer%E2%80%93Moore_majority_vote_algorithm)
