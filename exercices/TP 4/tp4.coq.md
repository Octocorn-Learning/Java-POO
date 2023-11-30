# TP 4 : La kalax !

## Objectifs 🎯

Vous devez créer et concevoir une kalax virtuelle.

Kalax est un meuble IKEA qui permet de ranger des objets.

## Consignes 📝

- À partir des User Stories et des Gherkins, vous devez créer les classes.
- Vous devrez ensuite créer les classes à proprement parler.

### Rendu 📦

- Vous devez créer un projet Maven et le déposer sur GitHub.
- Votre README.md doit contenir le diagramme de classe de votre projet.
- Vous devez créer une classe `Main` qui permet de tester votre code.

> En présentiel, vous devrez présenter votre diagramme de classe à l'oral !

## User Story 📝

Pour vous faciliter le travail, l'ensemble des fonctionnalités de la Kalax ont été rédigés sous forme de User Story.
Du Gherkin est également disponible pour vous aider à comprendre les comportements attendus.

Utilisez les exemples donnés dans vos tests (classe `Main`) ou si vous le souhaitez, dans vos tests unitaires.

> Il faudra donc créer les classes qui vont avec les objets ! 😉

### US 1 📖

```gherkin
Feature: Kalax
  En tant que client IKEA, je veux pouvoir choisir le nombre de box de ma kalax (4, 6 ou 8) afin de pouvoir adapter la taille de ma kalax à mes besoins.

  Scenario: Création d'une kalax
    Given je choisis une Kalax
    When Je souhaite une Kalax à <nombre de box> box
    Then la kalax a <nombre de box> box
    
  Exemples:
  | nombre de box |
  | 4             |
  | 6             |
  | 8             |

  Scenario: Mauvais choix de nombre de box
    Given je choisis une Kalax
    When Je souhaite une Kalax à 10 box
    Then je ne peux pas avoir une kalax à 10 box
```

## US 2 📖

```gherkin
Feature: Kalax
  En tant que client IKEA, je veux pouvoir choisir la couleur de ma kalax (blanc, noir, bois, etc) afin de pouvoir l'assortir à ma décoration.

  Scenario: Choix de la couleur
    Given je choisis une Kalax
    When Je souhaite une Kalax de couleur blanche
    Then la kalax est blanche

  Scenario:
    Given je choisis une Kalax
    When Je souhaite une Kalax de couleur noire
    Then la kalax est noire

  Scenario:
    Given je choisis une Kalax
    When Je souhaite une Kalax de couleur bois
    Then la kalax est bois
```

## US 3 📖

```gherkin
Feature: Box de kalax
  En tant que client IKEA, je veux pouvoir ajouter un composant une boxe à ma kalax (tiroir, porte, caisse) afin de pouvoir y ranger des objets.

  Scenario: Ajout d'un composant
    Given j'ai une Kalax
    When je souhaite ajouter un <composant> à une box
    Then la box a un <composant>
  Exemples:
  | composant |
  | tiroir    |
  | porte     |
  | caisse    |

  Scenario:  Ouvrir un composant
    Given j'ai une Kalax
    When je souhaite ouvrir un <composant>
    Then je peux consulter son contenu
    And je peux ajouter un objet dans le <composant>
  Exemples:
  | composant |
  | tiroir    |
  | porte     |
  | caisse    |

  Scenario: Ajouter un objet dans un composant
    Given j'ai une Kalax
    When je souhaite ajouter un <objet> dans un <composant>
    And le <composant> est ouvert
    Then le <composant> contient un <objet>
  Exemples:
  | composant | objet |
  | tiroir    | livre |
  | porte     | livre |
  | caisse    | vêtement |
```

## US 4 📖

```gherkin
Feature: Box de kalax
    En tant que client IKEA, je veux pouvoir ranger des objets dans les boxes de ma kalax afin de les entreposer.

    Scenario: Rangement d'un objet dans une box
        Given une kalax
        When je place une statue de licorne dans une box
        Then la box contient un objet
    Scenario: Rangement de plusieurs objets dans une box
        Given une kalax
        When je place deux livres dans une box
        Then la box contient deux livres
    Scenario: Rangement d'un objet dans une box ayant déjà un objet
        Given une kalax
        When je place une statue de licorne dans une box 
        And la box contient déjà un livre
        Then la box contient un livre et une statue de licorne
    Scenario: 
        Given une kalax
        When je place une statue de licorne dans une box 
        And la box contient un composant
        Then je ne peux pas placer la statue de licorne dans la box
```

## US 5 📖

```gherkin
Feature: Contenu Box
    En tant que client IKEA, je veux pouvoir consulter le contenu d'une box afin de savoir ce qu'elle contient.

    Scenario: Consultation du contenu d'une box
        Given il y a un liste dans la boxe 3 de ma kalax
        When je consulte le contenu de la box
        Then je vois le contenu de la box
    Scenario: 
      Given il y a un livre dans une caisse de ma kalax
      When je consulte le contenu de la boxe
      Then je vois le contenu de la caisse
```
