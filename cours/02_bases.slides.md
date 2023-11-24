---
title: Java POO - Bases
theme: solarized
author: Alexandre Devos
company: Octocorn
contributors: 
  - Alexandre Devos
sources:
  - 
---

# Java - Bases

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Java
### Hello World

Créez un nouveau projet Java **IntelliJ** :
- File > New > Project > New Project
- Sélectionnez l'archétype **Maven**
- Dans les options avancées, ajoutez votre nom de domaine inversé (ex: `fr.octocorn`)
- Laissez coché "Generate Sample Code"

----

## Java
### Hello World

Le projet a automatiquement été créé avec la structure suivante :

```
└───src # Racine du code source
    ├───main # Code source principal
    │   ├───java # Code source Java
    │   │   └───fr # Dossier contenant le nom de domaine inversé
    │   │       └───octocorn # On parle de package
    │   │               Main.java # Fichier contenant la classe Main
    │   │
    │   └───resources # Code source non Java
    └───test # Code source de tests
```

----

## Java
### Hello World

La classe `Main` est la classe principale du programme. 
Elle contient la méthode `main` qui est la méthode principale du programme.

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

> `System.out.println` permet d'afficher du texte dans la console

----

## Java
### Hello World

Pour exécuter le programme en ligne de commande :

```shell
java src/main/java/fr/octocorn/Main.java
```

> Vous pouvez aussi utiliser le bouton "Run" dans IntelliJ !

----

## Java
### JavaDoc

> Quelle est la différence entre un commentaire et une documentation ?

----

## Java
### JavaDoc

La documentation est un commentaire **structuré** et **formaté**.

```java
/**
 * Cette classe représente une personne
 */
public class Personne {
    // Code ...
}
```

> Elle peut être lue depuis n'importe où en passant la souris sur le code !

----

## Java
### JavaDoc

La documentation peut être **formatée** avec des balises HTML.

```java
/**
 * Cette classe représente une personne
 * <p>
 *     Une personne est caractérisée par son nom et son prénom
 * </p>
 */
public class Personne {
    // Code ...
}
```

----

## Java
### Commentaire

Le commentaire est un texte **libre**.

```java
// Cette classe représente une personne
public class Personne {
    // Code ...
}
```

- Elle ne peut pas être formatée
- Elle ne peut pas être lue depuis n'importe où

----

## Java
### Commentaire

Le commentaire peut être **multi-lignes**.

```java
/*
 * Cette classe représente une personne
 */
public class Personne {
    // Code ...
}
```

----

## Java
### Commentaire ou doc ?

- **Commentaire** : Pour expliquer le code
- **Documentation** : Pour décrire le code

> En théorie, il ne devrait pas y avoir de commentaire dans le code si le code est bien écrit !

----

## Java
### DOCUMENTEZ !

Si en théorie, un code bien écrit n'a pas besoin de documentation :
- La documentation est **obligatoire** pour les classes et les méthodes publiques
- La documentation est **fortement recommandée** pour les classes et les méthodes privées

> Bonne pratique ! 🤓

---

## Variables

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Variables
### Définition

Une variable est une **zone mémoire** dans laquelle on peut stocker une **valeur**.

```java
int age = 18;
```

- `int` est le **type** de la variable
- `age` est le **nom** de la variable
- `18` est la **valeur** de la variable

> Une variable est une **référence** vers une valeur

----

## Variables
### Définition

- Elle est stockée dans la **mémoire vive** de l'ordinateur
- Sa taille est allouée dynamiquement en fonction de son type
- Elle peut être modifiée à tout moment
- Elle peut être **référencée** par son nom

----

## Variables
### Nommage

- Bien nommer ses variables est **très important**
- Utilisez des noms **significatifs** et **compréhensibles**
- Pas d'**acrônyme** ou d'**abréviation** (sauf si connu de tous)
- Ils sont déclarés en **camelCase**

> Vous ne codez pas pour vous, mais pour les autres !

----

## Constantes
### Définition

- Une constante est une variable dont la valeur ne peut pas être modifiée
- Elle est déclarée avec le mot clé `final`

```java
final int AGE_LIMITE = 18;
```

> Les constantes sont déclarées en **majuscules**

----

## Variables
### Types numériques

- En java, les types sont précisés **avant** le nom de la variable
- Il existe plusieurs types numériques :
  - `byte` : 8 bits
  - `short` : 16 bits
  - `int` : 32 bits
  - `long` : 64 bits
  - `float` : 32 bits (virgule flottante)
  - `double` : 64 bits (virgule flottante)

----

## Variables
### Types booléens

- `boolean` : Vrai ou faux (1 bit)

```java
boolean estVrai = true;
boolean estFaux = false;
```

----

## Variables
### Types caractères

- `char` : Caractère unique (16 bits)
- `String` : Chaine de caractères (tableau de `char`)

```java
char lettre = 'a';
String mot = "Bonjour";
```

> Les `String` se déclarent avec `""` !

----

## Variables
### String

> Pourquoi `String` et pas `string` ?

----

## Variables
### String

- `String` est une **classe** et non un **type primitif**
- Les classes commencent par une **majuscule**
- Il s'agit d'un tableau de `char`, livré avec des méthodes

----

## Types
### Types primitifs VS Classes

- Les types primitifs sont **plus rapides** à manipuler
- Les classes sont **plus pratiques** à manipuler
- Elles ajoutent des **méthodes** et des **fonctionnalités**

> Les classes sont des **wrappers** des types primitifs

---

## Opérateurs

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Opérateurs
### Définition

Un opérateur est un **symbole** qui permet d'effectuer une **opération** sur des variables.

```java
int a = 1;
int b = 2;
int c = a + b;
```

- `+` est l'**opérateur d'addition**
- `a` et `b` sont les **opérandes**
- `c` est le **résultat** de l'opération

----

## Opérateurs
### Opérateurs arithmétiques

- `+` : Addition
- `-` : Soustraction
- `*` : Multiplication
- `/` : Division
- `%` : Modulo (reste de la division)

> Les opérateurs arithmétiques ne fonctionnent qu'avec des nombres !

----

## Opérateurs
### Opérateurs de comparaison

- `==` : Egalité
- `!=` : Différence
- `>` : Supérieur
- `<` : Inférieur
- `>=` : Supérieur ou égal
- `<=` : Inférieur ou égal

> Les opérateurs de comparaison renvoient un booléen !

----

## Opérateurs
### Opérateurs logiques

- `&&` : ET (Conjonction)
- `||` : OU (Disjonction)
- `!` : NON (Négation)

----

## Opérateurs
### Opérateurs d'incrémentation

- `++` : Incrémentation
- `--` : Décrémentation

```java
int a = 1;
a++; // a = a + 1
a--; // a = a - 1
```

> Peut être placé avant ou après la variable

----

## Opérateurs
### Concaténation

- `+` : Concaténation
- Equivalent : Méthode `concat` de la classe `String

```java
String a = "Hello";
String b = "World";
String c = a + " " + b; // "Hello World"
```

> La concaténation ne fonctionne qu'avec des `String` !

----

## Opérateurs
### Opérateurs d'affectation

- `=` : Affectation
- `+=` : Affectation avec addition
- `-=` : Affectation avec soustraction
- `*=` : Affectation avec multiplication

----

## Opérateurs
### Opérateurs ternaires

- `? :` : Opérateur ternaire
- Comparable à un `if` / `else`

```java
int a = 1;
int b = 2;
int c = a > b ? a : b; // c = b
```

> Eviter de l'utiliser, préférer un `if` / `else` !

---

## Conditions et boucles

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Conditions
### Définition

Une condition est une **instruction** qui permet d'effectuer une **action** en fonction d'une **condition**.

```java
int a = 1;
int b = 2;
if (a > b) {
    System.out.println("a est supérieur à b");
} else {
    System.out.println("a est inférieur ou égal à b");
}
```

> `if` signifie "si" en anglais

----

## Boucles
### for

Une boucle est une **instruction** qui permet d'effectuer une **action** plusieurs fois.

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

> Variable `i` : bien ou pas bien ?

Note: Pas bien ! 😱

----

## Boucles
### for

- Bien que très utilisé, la variable `i` n'est pas très parlante
- Il est préférable d'utiliser une variable plus parlante

```java
for (int index = 0; index < 10; index++) {
    System.out.println(index);
}
```

> Ca coute rien et c'est plus clair !

----

## Boucles
### for : les dérives

- Il est possible de stocker des boucles dans des boucles
- Les dérives connues consistent à nommer les index `i`, `j`, `k`, `l`, ...

```java
for (int i = 0; i < 10; i++) {
    for (int j = 0; j < 10; j++) {
        for (int k = 0; k < 10; k++) {
            for (int l = 0; l < 10; l++) {
                // ...
            }
        }
    }
}
```

> Résultat : un code illisible ! 😱

----

## Boucles
### while

- La boucle `while` permet de répéter une action **tant qu'une condition est vraie**
- La condition est vérifiée **avant** l'exécution de la boucle

```java
int i = 0;
while (i < 10) {
    System.out.println(i);
    i++;
}
```

> `while` signifie "tant que" en anglais

----

## Boucles
### do while

- La boucle `do while` permet de répéter une action **tant qu'une condition est vraie**
- La condition est vérifiée **après** l'exécution de la boucle

```java
int i = 0;
do {
    System.out.println(i);
    i++;
} while (i < 10);
```

---

## Tableaux

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Tableaux
### Définition

- Un tableau est une **structure de données** qui permet de stocker plusieurs valeurs.
- Il a une taille **fixe** et **définie** à l'avance
- Il est **indexé** à partir de 0

```java
int[] tableau = new int[10];
```

> `int[]` est le type du tableau : tableau d'entiers

----

## Tableaux
### Ajouter des éléments

- Il est possible d'ajouter des éléments dans un tableau
- Il faut pour cela utiliser l'**index** du tableau

```java
int[] tableau = new int[10];
tableau[0] = 1;
tableau[1] = 2;
tableau[2] = 3;
```

> Attention à ne pas dépasser la taille du tableau !

----

## Tableaux
### Ajouter lors de la création

- Il est possible d'ajouter des éléments lors de la création du tableau
- Il faut pour cela utiliser des **accolades** et séparer les éléments par des **virgules**

```java
int[] tableau = new int[] {1, 2, 3};
```

> Sa taille sera fixée automatiquement !

----

## Tableaux
### Parcourir un tableau

- Il est possible de parcourir un tableau avec une boucle
- Il faut pour cela utiliser la **taille** du tableau

```java
int[] tableau = new int[10];
for (int index = 0; index < tableau.length; index++) {
    System.out.println(tableau[index]);
}
```

> `tableau.length` permet de récupérer la taille du tableau

----

## Tableaux
### for-each

- Il est possible de parcourir un tableau avec une boucle `for-each`
- Il faut pour cela utiliser le mot clé `for` suivi du type de la variable, puis du nom de la variable, puis du tableau

```java
int[] tableau = new int[10];
for (int element : tableau) {
    System.out.println(element);
}
```

> Pas de valeur = valeur par défaut du type

----

## Tableaux
### Agrandir un tableau

- Il est possible d'agrandir un tableau
- Il faut pour cela créer un nouveau tableau avec la nouvelle taille
- Il faut ensuite copier les éléments du tableau dans le nouveau tableau

```java
int[] tableau = {1, 2, 3};
int[] nouveauTableau = new int[20];
for (int index = 0; index < tableau.length; index++) {
    nouveauTableau[index] = tableau[index];
}
tableau = nouveauTableau;
```

----

## Tableaux
### Tableaux multidimensionnels

- Un tableau peut contenir d'autres tableaux
- Il s'agit d'un tableau de tableaux

```java
int[][] tableau = new int[10][10];
```

> `int[][]` est le type du tableau : tableau de tableaux d'entiers

----

## Tableaux
### Tableaux multidimensionnels

- On utilisera l'index pour accéder aux éléments
- Il faut pour cela utiliser l'index du tableau, puis l'index de l'élément

```java
int[][] tableau = new int[10][10];
tableau[0][0] = 1;
tableau[0][1] = 2;
tableau[0][2] = 3;
```

> Attention à ne pas dépasser la taille du tableau !

----

## Tableaux
### ArrayList

- `ArrayList` est une classe qui permet de créer des tableaux dynamiques
- Il est possible d'ajouter des éléments sans se soucier de la taille

```java
ArrayList<Integer> tableau = new ArrayList<>();
tableau.add(1);
```

> `ArrayList` est une classe générique, il faut donc préciser le type

----

## Tableaux
### ArrayList

- `ArrayList` est une implémentation de l'interface `List`
- Il est possible de récupérer un tableau à partir d'une `List`

```java
List<Integer> liste = new ArrayList<>();
liste.add(1);
```

```java
Integer[] tableau = liste.toArray(new Integer[0]);
```

----

## Integer ?!

- `int` est un type primitif, `Integer` est une classe
- Comme pour `String`, `Integer` est une classe qui permet de manipuler des `int`

```java
int a = 1;
Integer b = 2;
```

> `Integer` est un **wrapper** de `int`

----

## Tableaux
### ArrayList

- `List` sert aussi d'interface pour le type `LinkedList`
- `LinkedList` est une implémentation de `List` qui permet d'ajouter des éléments plus rapidement

```java
List<Integer> liste = new LinkedList<>();
liste.add(1);
```

> `LinkedList` est une liste chaînée, elle est plus lente à parcourir

---

## Fonctions

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Fonctions
### Définition

Une fonction est une **sous-routine** qui permet d'effectuer une **action**.

```java
public void afficherBonjour() {
    System.out.println("Bonjour");
}
```

> `void` signifie "vide" en anglais

----

## Fonctions
### Syntaxe

```java
public <type> <nom>(<paramètres>) {
    // Code
}
```

- `public` : Visibilité de la fonction
- `<type>` : Type de retour de la fonction
- `<nom>` : Nom de la fonction
- `<paramètres>` : Paramètres de la fonction
- `{}` : Corps de la fonction

----

## Fonctions
### Visibilité

Il existe plusieurs visibilités pour les fonctions :
- `public` : Fonction accessible depuis n'importe où
- `private` : Fonction accessible uniquement depuis la classe
- `protected` : Fonction accessible depuis la classe et les classes filles
- `package` : Fonction accessible uniquement depuis le package

> Par défaut, la visibilité est `package`

----

## Fonctions
### Type de retour

- Dans tous les autres cas, la fonction retourne un type ou `void`
- `void` : Fonction qui ne retourne rien

```java
public int addition(int a, int b) {
    return a + b;
}
```

> `return` permet de retourner une valeur

----

## Fonctions
### Paramètres

Les paramètres sont des variables qui permettent de passer des valeurs à la fonction.

```java
public void afficherBonjour(String nom) {
    System.out.println("Bonjour " + nom);
}
```

> Les paramètres sont séparés par des virgules

----

## Fonction
### Appel

Pour appeler une fonction, il faut utiliser son nom suivi des paramètres entre parenthèses.

```java
afficherBonjour("Alexandre");
```

> Les paramètres doivent correspondre aux types attendus par la fonction

----

## Fonction
### Nomenclaure

- Les fonctions doivent être nommées de manière **significative**
- Elles doivent commencer par un **verbe** à l'infinitif
- Elles doivent être **courtes** et **concises**
- On utilisera le **camelCase** pour les nommer

----

## Fonction
### Bonnes pratiques

- Une fonction doit faire **une seule chose**
- Une fonction doit faire moins de **20 lignes**
- Idéalement, une fonction est **documentée** avec de la **JavaDoc**

> Le nom de la fonction est souvent inversement proportionnel à sa taille/complexité

----

## Fonction
### Exemple

```java
/**
 * Affiche un message de bienvenue personnalisé
 * @param nom Le nom de la personne
 */
public void afficherBonjour(String nom) {
    System.out.println("Bonjour " + nom);
}
```

----

## Fonction
### Découpage

- Une fonction doit faire **une seule chose**
- Si elle fait plus de 20 lignes, il faut la découper en plusieurs fonctions

```java
public void afficherBonjour(String nom) {
    System.out.println("Bonjour " + nom);
}
```

> Ici, la fonction ne fait qu'une seule chose, elle est donc bonne !

----

## Fonction
### Découpage

```java
/**
 * Affiche le message de bienvenue et vérifie si la personne est majeure
 */
public void afficherBonjourEtVerifierAge(String nom, int age) {
    System.out.println("Bonjour " + nom);
    if (age >= 18) {
        System.out.println("Vous êtes majeur !");
    } else {
        System.out.println("Vous êtes mineur !");
    }
}
```

> Ici, la fonction fait deux choses, il faut la découper !

----

## Fonction
### Découpage

```java
/**
 * Affiche le message de bienvenue
 */
private void afficherBonjour(String nom) {
    System.out.println("Bonjour " + nom);
}

/**
 * Vérifie si la personne est majeure
 */
private void verifierAge(int age) {
    if (age >= 18) {
        System.out.println("Vous êtes majeur !");
    } else {
        System.out.println("Vous êtes mineur !");
    }
}

/**
 * Affiche le message de bienvenue et vérifie si la personne est majeure
 */
public void afficherBonjourEtVerifierAge(String nom, int age) {
    afficherBonjour(nom);
    verifierAge(age);
}
```

---

## Classes et objets

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Objets
### Définition

Un objet est une **instance** d'une **classe**.

```java
Personne Alex = new Personne();
```

- `Personne` est le **type** de l'objet
- `Alex` est le **nom** de l'objet

> `new` permet d'instancier un objet

----

## Classes
### Définition

Une classe est un **modèle** qui permet de créer des objets.

```java
public class Personne {
    // Code
}
```

- `public` : Visibilité de la classe
- `class` : Mot clé pour définir une classe
- `Personne` : Nom de la classe
- `{}` : Corps de la classe

----

## Classes
### Attributs

Les attributs sont des variables qui permettent de stocker des valeurs dans un objet.

```java
public class Personne {
    public String nom;
    public int age;
}
```

> Les attributs sont déclarés dans la classe

----

## Classes
### Méthodes

Les méthodes sont des fonctions qui permettent d'effectuer des actions sur un objet.

```java
public class Personne {
    public String nom;
    public int age;

    public void etudier(String matiere) {
        System.out.println(nom + " étudie " + matiere);
    }
}
```

----

## Classes
### Constructeur

Le constructeur est une méthode qui permet d'initialiser un objet.

```java
public class Personne {
    public String nom;
    public int age;

    public Personne(String nom, int age) {
        this.nom = nom;
        this.age = age;
    }
}
```

- Il porte le même nom que la classe
- Appelé lors de l'instanciation
- Permet d'initialiser les attributs

----

## Classes
### Précisions

```java
public class Personne {
    public String nom;
    public int age;

    public Personne(String nom, int age) {
        this.nom = nom;
        this.age = age;
    }
}
```

- `this` permet de faire référence à l'objet courant
- `this.nom` fait référence à l'attribut `nom` de l'objet courant
- `nom` fait référence au paramètre `nom` de la méthode

----

## Classes
### Statique

- Une classe peut être **statique**
- Une classe statique ne peut pas être instanciée
- Elle ne peut contenir que des méthodes statiques

```java
public static class Personne {
    // Code
}
```

> `static` permet de définir une classe statique

----

## Classes
### Statique

- L'objectif des classes statique est souvent de regrouper des méthodes
- Elles sont souvent utilisées pour créer des **utilitaires**

```java
public static class Mathematiques {
    public static int addition(int a, int b) {
        return a + b;
    }
}
```

----

## Classes
### Attributs statiques

- Attributs qui appartiennent à la classe et non à l'objet
- Partagés par tous les objets de la classe

```java
public class Personne {
    public static int nombreDePersonnes = 0;

    public Personne() {
        nombreDePersonnes++;
    }
}
```
Ici, on incrémente le nombre de personnes à chaque fois qu'on instancie un objet

----

## Classes
### Attributs `final`

- `final` devant un attribut signifie qu'il est **constant**
- Il ne peut pas être modifié après son initialisation
- Comme une constante, qui serait initialisée dans le constructeur

```java
public class Personne {
    public final String nom;

    public Personne(String nom) {
        this.nom = nom;
    }
}
```

----

## Classes
### Classes par défaut

- Il existe de nombreuses classes existantes en Java
- Elles sont disponibles par défaut dans le langage mais doivent être importées
- Elles sont regroupées dans des **packages**

```java
import java.util.ArrayList;
```

> `import` permet d'importer une classe

----

## Classes
### Bonnes pratiques

- Une classe doit être **documentée** avec de la **JavaDoc**
- Elle est **publique** si elle est utilisée par d'autres classes
- Une classe = un fichier !
- Elle est nommée en **PascalCase**
- Elle n'a qu'une seule **responsabilité**

> Nous aborderons ça plus en détail dans les prochains cours !

---

## Packages

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Packages
### Définition

- Un package est un **dossier** qui contient des classes
- Il permet de **regrouper** les classes par **thème**
- Il permet de **structurer** le code

```java
package fr.octocorn;

public class Personne {
    // Code
}
```

> `package` permet de définir le package de la classe

----

## Packages
### Structure

- Les packages sont définis par un **nom de domaine inversé**
- Il convient d'organiser ses packages en début de projet
- Il est possible de créer des sous-packages

----

## Packages
### Structure

```shell
└───src
    ├───main
    │   ├───java
    │   │   └───fr
    │   │       └───octocorn
    │   │           └───cours
    │   │               └───java
    │   │                   └───Personne.java
    │   │
    │   └───resources
    └───test
```

> `fr.octocorn.cours.java` est le package de la classe `Personne`

----

## Packages
### Bonnes pratiques

- Un package par **thème** ou par **fonctionnalité**
- Un package = un dossier !
- Il est nommé en **minuscules**
- Il est nommé en **singulier**

> Il n'y a pas de règles strictes, mais il faut rester cohérent !

----

## Packages
### Importer

- Il est possible d'importer un package
- Il faut pour cela utiliser le mot clé `import` suivi du nom du package

```java
import fr.octocorn.cours.java.Personne;

public class AnimalDeCompagnie {
    public Personne maitre;
}
```

> `import` permet d'importer un package

---

# Exceptions

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Exceptions
### Définition

- Une exception est une **erreur** qui se produit lors de l'exécution d'un programme
- Elle peut être **gérée** ou **non gérée**
- Elle interrompt l'exécution du programme

----

## Exceptions
### Gérée

- Une exception gérée est une exception qui est **attrapée** par le programme
- Elle est **gérée** par le programme
- Elle n'interrompt pas l'exécution du programme
- On peut définir un comportement à adopter en cas d'exception

```java
try {
    // Si ce code throw une exception...
} catch (Exception e) {
    // Elle est attrappée ici ! On peut définir un comportement
}
```


----

## Exceptions
### Non gérée

- Une exception non gérée est une exception qui n'est pas **attrapée** par le programme
- Elle n'est pas **gérée** par le programme
- Elle interrompt l'exécution du programme

```java
public void lancerException() {
    throw new Exception("Erreur !");
}
```

> `throw` permet de lancer une exception

----

## Exceptions
### Types

- Il existe de nombreux types d'exceptions
- Elles sont regroupées dans des **packages**
- Elles sont souvent **héritées** d'une classe `Exception`

```java
import java.io.IOException;

public void lancerException() throws IOException {
    throw new IOException("Erreur !");
}
```

----

## Exceptions
### Types

- `ArrayIndexOutOfBoundsException` : Index de tableau invalide
- `ClassNotFoundException` : Classe non trouvée
- `NullPointerException` : Pointeur null
- `IllegalArgumentException` : Paramètre invalide 
- `IOException` : Entrée / Sortie
- `NumberFormatException` : Format de nombre invalide

----

## Exceptions
### Créer une exception

- Il est possible de créer ses propres exceptions
- Il faut pour cela créer une classe qui hérite de `Exception`

```java
public class MonException extends Exception {
    public MonException(String message) {
        super(message);
    }
}
```

> `super` permet d'appeler le constructeur de la classe parente

----

## Exceptions
### Lancer une exception

- Il est possible de lancer une exception
- Il faut pour cela utiliser le mot clé `throw` suivi de l'exception

```java
public void lancerException() throws MonException {
    throw new MonException("Erreur !");
}
```

> `throws` permet de déclarer une exception

----

## Exceptions
### Bonnes pratiques

- Créez si nécessaire vos propres exceptions !
- Une exception doit être **documentée** avec de la **JavaDoc**
- Elle doit être **gérée** si elle peut l'être
- Elles sont suffixées par `Exception`

> Les bonnes pratiques de nommage s'appliquent aussi aux exceptions !

----

## Exceptions
### Démonstration

Créons une exception personnalisée !

---

# HashMap

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## HashMap
### Définition

- Structure de données faisant parie du Framework de Collections
- Dans le package `java.util`
- Sert à stocker des données sous forme de clé / valeur
- C'est une implémentation de l'interface `Map`

----

## HashMap
### Constitution

- Une `HashMap` est constituée de **paires** clé / valeur
- La clé est unique
- La valeur peut être dupliquée

```json
"index1": {
    "clé1": "valeur1",
    "clé2": "valeur2",
    "clé3": "valeur3"
},
"index2": {
    "clé1": "valeur1",
    "clé2": "valeur2",
    "clé3": "valeur3"
}
```

----

## HashMap
### Avantages

- Les clefs sont uniques et servent d'index
- Les recherches sont très rapides
- Les données sont triées par ordre d'insertion

----

## HashMap
### Syntaxe

Pour créer une `HashMap` :

```java
Map<String, String> map = new HashMap<>();
```

----

## HashMap
### Les méthodes

- `put()` : Ajouter une valeur
- `get()` : Récupérer une valeur
- `remove()` : Supprimer une valeur
- `containsKey()` : Vérifier si une clé existe
- `containsValue()` : Vérifier si une valeur existe
- `keySet()` : Récupérer les clés
- `values()` : Récupérer les valeurs
- `entrySet()` : Récupérer les paires clé / valeur

----

## HashMap
### Exemple

```java
Map<String, String> map = new HashMap<>();
map.put("cle1", "valeur1");
map.get("cle1"); // valeur1
map.remove("cle1");
map.containsKey("cle1"); // false
map.containsValue("valeur1"); // false
map.keySet(); // [cle1]
map.values(); // [valeur1]
map.entrySet(); // [cle1=valeur1]
```

----

## HashMap
### Parcourir

- Il est possible de parcourir une `HashMap` avec une boucle `for-each`
- Il faut pour cela utiliser la méthode `entrySet()`

```java
Map<String, String> map = new HashMap<>();
for (Map.Entry<String, String> entry : map.entrySet()) {
    System.out.println(entry.getKey() + " : " + entry.getValue());
}
```

> `entrySet()` permet de récupérer les paires clé / valeur

----

## HashMap
### Démonstration !

Gestion d'élèves avec une `HashMap` !

Note: `./Espace Formateur/demos/hashmap.md`

---

# A vous de jouer !

Réalisez le TP 1 !

Note: `exercices/tp1/tp1.coq.md`

---

# La suite !

- [Index](index.html)