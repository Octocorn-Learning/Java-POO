---
title: POO - Encapsulation
theme: solarized
author: Alexandre Devos
company: Octocorn
contributors: 
  - Alexandre Devos
sources:
  - 
---

## Les accesseurs

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Les accesseurs
### Définition

- Les **accesseurs** sont des **méthodes** qui permettent d'**accéder** aux **attributs** d'une classe.
- Il existe deux types d'accesseurs :
  - **getters** : permettent de **récupérer** la valeur d'un attribut.
  - **setters** : permettent de **modifier** la valeur d'un attribut.

----

## Les getters
### Définition

- Les **getters** sont des **méthodes** qui permettent de **récupérer** la valeur d'un attribut.
- Ils sont **obligatoires** pour chaque attribut **privé**.
- Ils sont **optionnels** pour chaque attribut **public**.

----

## Les getters
### Syntaxe

- Les getters se déclarent comme des **méthodes** "classiques".
- Ils sont forcément **publics**.
- Ils commence par le mot clé `get` suivi du nom de l'attribut avec une majuscule.

```java
public String getNom() {
    return this.nom;
}
```

----

## Les getters
### Exemple

```java
public class Personne {
    private String nom;
    private String prenom;
    
    public String getNom() {
        return this.nom;
    }
    
    public String getPrenom() {
        return this.prenom;
    }
}
```

> Pourquoi s'embêter et ne pas mettre les attributs en public ?

----

## Les getters
### Intérêt

- Un attribut contient une valeur
- Un **getter** peut contenir de la logique

```java
public class Personne {
    private String nom;
    private String prenom;
    
    public String getNom() {
        return this.nom.toUpperCase();
    }
    
    public String getPrenom() {
        return this.prenom;
    }
}
```

----

## Les getters
### Acces

- Les **getters** sont **publics**.
- Ils sont donc **accessibles** depuis n'importe où.

```java
public class Main {
    public static void main(String[] args) {
        Personne personne = new Personne("Alexandre", "Devos");
        
        System.out.println(personne.getNom());
    }
}
```

----

## Les setters
### Définition

- Les **setters** sont des **méthodes** qui permettent de **modifier** la valeur d'un attribut.
- Ils sont **obligatoires** pour chaque attribut **privé**.
- Ils sont **optionnels** pour chaque attribut **public**.

----

## Les setters
### Syntaxe

- Les setters se déclarent comme des **méthodes** "classiques".
- Ils sont forcément **publics**.
- Ils commence par le mot clé `set` suivi du nom de l'attribut avec une majuscule.

```java
public void setNom(String nom) {
    this.nom = nom;
}
```

----

## Les setters
### Exemple

```java
public class Personne {
    private String nom;
    private String prenom;
    
    public void setNom(String nom) {
        this.nom = nom;
    }
    
    public void setPrenom(String prenom) {
        this.prenom = prenom;
    }
}
```

----

## Les setters
### Intérêt

- Comme pour les getters, un **setter** peut contenir de la logique.

```java
public class Personne {
    private String nom;
    private String prenom;
    
    public void setNom(String nom) {
        if (nom.length() > 2) {
            this.nom = nom;
        } else  {
            throw new IllegalArgumentException("Le nom doit contenir au moins 2 caractères.");
        }
    }
    
    public void setPrenom(String prenom) {
        this.prenom = prenom;
    }
}
```

----

## Accesseurs
### Dans le constructeur

- Il est possible d'utiliser les **setters** dans le **constructeur**.
- C'est utile pour **initialiser** les attributs et **vérifier** les valeurs.

```java
public class Personne {
    private String nom;
    private String prenom;
    
    public Personne(String nom, String prenom) {
        this.setNom(nom);
        this.setPrenom(prenom);
    }
    
    public void setNom(String nom) {
        if (nom.length() > 2) {
            this.nom = nom;
        } else  {
            throw new IllegalArgumentException("Le nom doit contenir au moins 2 caractères.");
        }
    }
    
    public void setPrenom(String prenom) {
        this.prenom = prenom;
    }
}
```

---

# Encapsulation

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Encapsulation
### Définition

- Demandez à n'importe quel développeur, 80% répondront : C'est de mettre des **getters** et des **setters**.
- Ce n'est pas si simple : **encapsulation** = **masquage**.
- L'encapsulation permet de **masquer** les **attributs**/**méthodes** d'une classe afin de cacher sa complexité.

----

## Encapsulation
### Définition

- L'accesseur n'est pas l'encapsulation, c'est un **moyen** d'**implémenter** l'encapsulation.
- Si j'utilise un marteau, je ne suis pas un charpentier. Mais si je suis charpentier, j'utilise un marteau.

----

## Encapsulation
### La logique

- Je n'ai pas besoin de savoir comment fonctionne une voiture pour l'utiliser.
- Le fonctionnement du moteur est **caché** sous le capot.
- De mon point de vue, je n'ai besoin que de **connaître** les **méthodes** qui me permettent d'**interagir** avec la voiture.
- Je n'ai pas besoin de savoir comment fonctionne le moteur pour **conduire** la voiture.

----

## Encapsulation
### Cas concrêt

- Vous devez créer un programme de paris en ligne.
- Il est reservé aux personnes majeures.
- Dans le cahier des charges **fonctionnel**, nous avons :

```plantuml
class Personne {
    +nom: String
    +prenom: String
    +age: int
}
```

> Comment cette information sera stockée en BDD ?

----

## Encapsulation
### Cas concrêt

- En BDD, nous n'allons pas stocker l'âge de la personne, mais sa date de naissance.
- Nous allons donc devoir **calculer** l'âge à partir de sa date de naissance.
- Nous allons donc devoir **masquer** la date de naissance et **exposer** l'âge.

> Du coup, avons-nous besoin de l'attribut **age** ?

----

## Démonstration

Résoudre le cas de l'âge

----

## Encapsulation
### Bonnes pratiques

> Faut-il systématiquement mettre ses attributs en privé ?

----

## Encapsulation
### Bonnes pratiques

- Pas nécessairement, mais c'est une bonne habitude à prendre.
- On a pas toujours besoin de masquer ses attributs ou de vérifier leurs valeurs.

> Faites preuve de bonne intelligence !

----

## Encapsulation
### Bonnes pratiques

> Faut-il systématiquement mettre des getters et des setters ?

----

## Encapsulation
### Bonnes pratiques

- **NON** : Mettez des getters et des setters **uniquement** si vous en avez besoin.
- Gardez séparée la logique **interne** de la logique **externe**.

> Si ça fait perdre du temps et n'apporte rien, pourquoi le faire ?

----

## A vous de jouer !

Réalisez le TP 2