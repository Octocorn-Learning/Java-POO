---
title: Design Patterns
theme: solarized
author: Alexandre Devos
company: Octocorn
contributors:
  - Alexandre Devos
sources:
  - https://refactoring.guru/
---

# Design patterns

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Design patterns

### Définition

- Patron de conception
- Un design pattern est une **solution** à un **problème récurrent**
- Elle est **éprouvée** et **documentée**

----

## Design patterns

### Origines

- 1977 : Christopher Alexander publie *A Pattern Language*
- Il contient des solutions à des problèmes d'architecture urbaine
- L'idée est reprise par "The Gang of Four" en 1994

----

## Design patterns

### The Gang of Four

- Erich Gamma, Richard Helm, Ralph Johnson et John Vlissides
- Ils publient *Design Patterns: Elements of Reusable Object-Oriented Software* en 1994
- Ils y décrivent 23 design patterns classés en 3 catégories

> Titre trop long, il est souvent abrégé en *The GoF Book*

----

## Design patterns

### The GoF Boof

- Ils traitent 23 cas communs de développement et proposent une solution pour chacun
- Concernent initialement le C++, mais peut être appliqué à tous les langages orientés objet
- Ils mettent un nom sur ces usages, et les classent en 3 catégories :
    - Création
    - Structure
    - Comportement

----

## Design patterns

### Création

- Abstract Factory
- Builder
- Factory Method
- Prototype
- Singleton

> Désigne la manière de créer des objets
----

## Design patterns

### Structure

- Adapter
- Bridge
- Composite
- Decorator
- Facade
- Flyweight
- Proxy

> Désigne la manière de structurer les classes et les objets

----

## Design patterns

### Comportement

- Chain of Responsibility
- Command
- Interpreter
- Iterator
- Mediator
- Memento

> Désigne la manière de gérer les interactions entre les objets

----

## Design patterns

### Comportement (suite)

- Observer
- State
- Strategy
- Template Method
- Visitor

> Désigne la manière de gérer les interactions entre les objets

----

## Design patterns

### Utilisation

- Il ne s'agit pas "d'importer une lib" ou "d'ajouter une dépendance"
- C'est une réflexion sur la manière de résoudre un problème
- Elles se veulent génériques et réutilisables

----

## Design patterns

### Dans ce cours

- Nous n'aborderons pas tous les design patterns dans ce cours
- Nous nous concentrerons sur une dizaine de design patterns les plus courants

----

## Design patterns

### Sources

- [The GoF Book](https://bit.ly/amazon-gof)
- [Refactoring Guru](https://refactoring.guru/)

----

## Design patterns

### Obligatoires ?

- Connaitre les design patterns est un plus, pas une obligation
- Il est important de connaitre les problèmes qu'ils résolvent
- Sur le principe : on pourrait coder pendant des années sans les connaitre !

> Vous en avez déjà utilisé sans le savoir !

----

## Design patterns

### Communiquer

- Les design patterns sont communs à tous les langages orientés objet
- Les connaitre permet de communiquer avec d'autres développeurs

---

# Design patterns

## Singleton

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Singleton

### Définition

- Le singleton est un design pattern de type *création*
- Il permet de s'assurer qu'une classe n'a qu'une seule instance !
- Elle fournit un accès global à cette instance

----

## Singleton

### Usages

- Lorsqu'on a besoin d'une classe qui ne doit exister qu'en un seul exemplaire
- Par exemple :
    - une classe qui gère les logs de l'application
    - Une classe pour la connection à une base de données
    - Une classe pour gérer les controllers dans un framework

----

## Singleton

### Implémentation

- Il existe plusieurs manières d'implémenter un singleton
- Nous allons voir la plus simple : le singleton "paresseux"
- Il s'agit d'une classe qui se crée elle-même lorsqu'on l'appelle pour la première fois
- Elle se crée donc au premier appel, et ne se recrée plus jamais

----

## Singleton

### Etapes

1. Création d'un constructeur **privé**
2. Création d'une variable **privée** et **statique** de type de la classe, nommé `instance`
3. Création d'un getter `getInstance()` qui retourne la variable `instance`
4. Dans le getter, si la variable `instance` est `null`, on la crée, sinon on la retourne

----

## Singleton

### Démonstration !

----

## Singleton

### Exemple

```java
public class Singleton {
    private static Singleton instance;

    private Singleton() {
    }

    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

----

## Singleton

### Exemple

```java
public class Main {
    public static void main(String[] args) {
        Singleton singleton = Singleton.getInstance();
    }
}
```

----

## Singleton

### Inconvénients

- Le singleton "paresseux" n'est pas *thread-safe* !
- Ne réspecte pas le SRP : il résout le problème d'unicité, mais aussi celui de la création
- Difficile à tester : il est impossible de mocker la classe (car le constructeur est privé)

Note: Si deux threads appellent `getInstance()` en même temps, deux instances seront créées (nb : une adaptation est
possible). Cf. partie facultative de la démo.

----

## Singleton

### Bonne pratique ?

- Le singleton est un design pattern très controversé
- S'il a longtemps été considéré comme une bonne pratique, il est aujourd'hui **déconseillé** 😱

> Pourquoi ?

----

## Singleton

### Dépendance forte

- Le singleton crée une **dépendance forte** entre les classes
- En cas de re-factorisation, c'est **très difficile** de s'en débarrasser !

> Les problèmes arrivent en général plus tard !

----

## Singleton

### Des abus

- Le singleton est souvent utilisé à tort et à travers
- Il arrive que ce soit pour camoufler un problème de conception

---

# Design patterns

## Factory

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Factory

### Définition

- Le factory est un design pattern de type *création*
- Il permet de créer des objets sans avoir à connaitre leur type à l'avance
- L'évolution du code est alors facilitée !

----

## Factory

### Cas concret

- Vous devez créer une application de gestion de transport de marchandises
- L'entreprise utilise exclusivement des camions.
- La majorité de la logique métier se trouve dans la classe `Truck`

----

## Factory

### Cas concret

- Puis, l'entreprise décide d'acheter des bateaux pour transporter des marchandises par voie maritime
- Elle vous demande un "petit changement" : prendre en compte les bateaux dans l'application
- Vous avez déjà un couplage très fort entre votre application et la classe `Truck`
- Le changement va être difficile !

----

## Factory

### La logique

- Ici, on va déléguer la construction des objets à une classe dédiée : la factory
- On appellera plus directement `new Truck()`, mais `factory.createTransport()` par exemple
- Nous créons alors une interface `Transport` qui sera implémentée par `Truck` et `Boat`

----

## Factory

### En image

![Factory](assets/factory-pattern.png)

----

## Factory

### Lexique

- **Product** : l'interface commune à tous les produits
- **ConcreteProduct** : les produits concrets qui implémentent l'interface
- **Creator** : la classe qui crée les factories
- **ConcreteCreator** : la factory concrète qui crée les produits concrets

----

## Factory

### En étapes

1. Création d'une interface (Product) qui contient les méthodes communes à tous les produits
2. Création des classes concrètes (ConcreteProduct) qui implémentent l'interface
3. Création d'une classe abstraite (Creator) qui contient la méthode de création de produits
4. Création d'une classe concrète (ConcreteCreator) qui implémente la méthode de création

----

## Factory

### Démonstration !

----

## Factory

### Nomenclature

- Dans les exemples, nous avons suffixé les classes (`Factory` -> `TruckFactory`)
- En général, les créators ont un nom représentatif **métier**. Les ConcreteCreator reprennent ce nom en suffixe.
- Ex: `Transporter` -> `TruckTransporter`, `BoatTransporter`

----

## Factory

### A vous de joeur !

Réaliser le TP 5 sur la Factory !


---

# Design patterns

## Builder

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Builder

### Définition

- Le builder est un design pattern de type *création*
- Il permet de créer des objets complexes étape par étape

----

## Builder

### Cas concret

- Vous devez créer une application pour construire des maisons
- Au début, c'est simple : 4 murs, un toit, une porte et des fenêtres
- Puis, on ajoute des options : un garage, une piscine, un jardin, etc.

> Quelle serait la solution la plus simple ?

----

## Builder

### Cas concret

- On pourrait créer une classe `House` avec pleins d'attributs nullables
- Puis pour chaque cas, on remplit les attributs concernés, ou on les met à null

> Solution simple, mais pas très propre !

----

## Builder

### Exemple

```java
public class House {
    private int walls;
    private int roof;
    private int door;
    private int windows;
    private int garage;
    private int pool;
    private int garden;
    private int chimney;
    private int solarPanel;
    private int alarm;
    private int airConditioning;
    private int heating;
    private int homeAutomation;
    private int elevator;
    private int cellar;
    private int balcony;
    private int terrace;
    private int veranda;

    public House(int walls,
                 int roof,
                 int door,
                 int windows,
                 int garage,
                 int pool,
                 int garden,
                 int chimney,
                 int solarPanel,
                 int alarm,
                 int airConditioning,
                 int heating,
                 int homeAutomation,
                 int elevator,
                 int cellar,
                 int balcony,
                 int terrace,
                 int veranda
    ) {
        this.walls = walls ??null;
        this.roof = roof ??null;
        this.door = door ??null;
        this.windows = windows ??null;
        this.garage = garage ??null;
        this.pool = pool ??null;
        this.garden = garden ??null;
        this.chimney = chimney ??null;
        this.solarPanel = solarPanel ??null;
        this.alarm = alarm ??null;
        this.airConditioning = airConditioning ??null;
        this.heating = heating ??null;
        this.homeAutomation = homeAutomation ??null;
        this.elevator = elevator ??null;
        this.cellar = cellar ??null;
        this.balcony = balcony ??null;
        this.terrace = terrace ??null;
        this.veranda = veranda ??null;
    }

    public int getWalls() {
        return walls;
    }

    public int getRoof() {
        return roof;
    }

    public int getDoor() {
        return door;
    }

    public int getWindows() {
        return windows;
    }

    public int getGarage() {
        return garage;
    }

    public int getPool() {
        return pool;
    }

    public int getGarden() {
        return garden;
    }

    public int getChimney() {
        return chimney;
    }

    public int getSolarPanel() {
        return solarPanel;
    }

    public int getAlarm() {
        return alarm;
    }

    public int getAirConditioning() {
        return airConditioning;
    }

    public int getHeating() {
        return heating;
    }

    public int getHomeAutomation() {
        return homeAutomation;
    }

    public int getElevator() {
        return elevator;
    }

    public int getCellar() {
        return cellar;
    }

    public int getBalcony() {
        return balcony;
    }

    public int getTerrace() {
        return terrace;
    }

    public int getVeranda() {
        return veranda;
    }

    public void setWalls(int walls) {
        this.walls = walls;
    }

    public void setRoof(int roof) {
        this.roof = roof;
    }

    public void setDoor(int door) {
        this.door = door;
    }

    public void setWindows(int windows) {
        this.windows = windows;
    }

    public void setGarage(int garage) {
        this.garage = garage;
    }

    public void setPool(int pool) {
        this.pool = pool;
    }

    public void setGarden(int garden) {
        this.garden = garden;
    }

    public void setChimney(int chimney) {
        this.chimney = chimney;
    }

    public void setSolarPanel(int solarPanel) {
        this.solarPanel = solarPanel;
    }

    public void setAlarm(int alarm) {
        this.alarm = alarm;
    }

    public void setAirConditioning(int airConditioning) {
        this.airConditioning = airConditioning;
    }

    public void setHeating(int heating) {
        this.heating = heating;
    }

    public void setHomeAutomation(int homeAutomation) {
        this.homeAutomation = homeAutomation;
    }

    public void setElevator(int elevator) {
        this.elevator = elevator;
    }

    public void setCellar(int cellar) {
        this.cellar = cellar;
    }

    public void setBalcony(int balcony) {
        this.balcony = balcony;
    }

    public void setTerrace(int terrace) {
        this.terrace = terrace;
    }

    public void setVeranda(int veranda) {
        this.veranda = veranda;
    }

    // Et toutes les autres méthodes...
}
```

OSKOUR ALED

----

## Builder

### Trop de paramètres, tue les paramètres

- On se retrouverait avec des paramètres souvent inutilisés
- A chaque nouveau besoin : on devrait modifier la classe `House`

> Pas très SOLID tout ça !

----

## Builder

### Cas concret

- On pourrait créer une classe `House` avec tous les attributs
- Puisqu'on respecte SOLID, on va créer des sous-classes pour chaque type de maison
    - `HouseWithGarage`, `HouseWithPool`, etc.
- Mais on va vite se retrouver avec des dizaines de sous-classes !

> La solution est plus simple, mais devient vite ingérable !

----

## Builder

### Solution : builder !

- On va créer une interface `Builder` qui va nous permettre de construire une maison
- Le builder contiendra différentes méthodes pour ajouter des options à la maison
- `buildDoor()`, `buildWindows()`, `buildGarage()`, etc.
- Et une méthode finale `build()` ou `getResult()` qui retourne la maison

----

## Builder

### Le Directeur

- Classe facultative, qui permet de définir des routines de construction
- Elle possède un attribut `builder` qui contient le builder
- Le Client peut appeler le directeur, ou directement le builder

----

## Builder

### En image

![Builder](assets/builder.png) <!-- .element width="40%" -->

----

## Builder

### Lexique

- **Director** : classe facultative qui définit des routines de construction
- **Builder** : interface qui définit les méthodes de construction
- **ConcreteBuilder** : classe qui implémente l'interface et construit les produits
- **Product** : le produit final
- **Client** : classe qui utilise le builder. S'adresse au directeur ou au builder directement

----

## Builder

### En étapes

1. On créé notre classe `House` qui contient les attributs de la maison
2. On créé notre interface `Builder` qui contient les méthodes de construction
3. On créé notre classe `HouseBuilder` qui implémente l'interface
4. On créé notre classe `HouseDirector` qui contient le builder et les méthodes de construction

----

## Builder

### Démonstration !

Créons notre petite maison !

---

# Design patterns

## Adapter

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

## Adapter

### Définition

- L'adapter est un design pattern de type *structure*
- Il permet de faire communiquer deux classes qui n'ont pas la même interface

----

## Adapter

### Cas concret

- Vous devez créer une application qui alimente ses données depuis une API externe
- Vous n'avez donc aucun contrôle sur le format/la forme des données
- La structure du JSON reçue est très différente de celle de votre application

> Vous créez un adaptateur pour transformer les données reçues en données utilisables

----

## Adapter

### Exemple

Données reçues :

```json
{
  "id": 1,
  "name": "Alexandre Devos",
  "email": "a.devos@octocorn.fr",
  "street": "Rue de la Paix",
  "city": "Paris",
  "zipcode": "75000",
  "country": "France",
  "phone": "0123456789",
  "entreprise": "Octocorn"
}
```

----

## Adapter

### Exemple

Données attendues :

```json
{
  "id": 1,
  "nom": "Alexandre Devos",
  "mail": "a.devos@octocorn.fr",
  "entreprise": {
    "denomination": "Octocorn",
    "telephone": "0123456789",
    "adresse": {
      "rue": "Rue de la Paix",
      "ville": "Paris",
      "codePostal": "75000",
      "pays": "France"
    }
  }
}
```

----

## Adapter

### En image

![Adapter](assets/adapter.png)

----

## Adapter

### Lexique

- **Client** : la classe qui utilise l'adapter
- **Adaptee** : classe incompatible (legacy, api ...), à adapter
- **Target** : l'interface que le **client** utilise. Ce en quoi il faut "convertir" l'**adaptee**
- **Adapter** : la classe qui adapte l'interface de l'adaptee à l'interface du client

----

## Adapter

### Dans notre cas

![Exemple Adapter](assets/adapter-exemple.png)

> Représentation simplifiée (sans interface)

----

## Adapter

### En étapes

1. Création du `Client` qui utilise l'adapter
2. Création du `Target` qui définit les méthodes utilisées par le client
3. Création de l'`Adaptee` qui contient l'objet à adapter
4. Création de l'`Adapter` qui implémente l'interface `Target` et agrège l'objet `Adaptee`

> Il peut arriver que certaines étapes soient déjà existantes

----

## Adapter

### Use Cases

- Pluguer une API externe à une application existante
- Refactorisation/nouvelle app basé sur une BDD existante (legacy)
- Décommissionner une API existante

----

## Adapter

### Démonstration !

---

# Design patterns

## Decorator

![Logo Java](./assets/java.png) <!-- .element width="20%" align="left" -->

![IntelliJ](assets/intellij.png) <!-- .element width="30%" align="right" -->

----

> En cours de rédaction