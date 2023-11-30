# TP 3 : Le Zoo

## Objectifs 🎯

Vous devez créer un Zoo virtuel.  
Il devra contenir des animaux de différentes espèces. Ces dernières sont catégorisées en 3 types : les mammifères, les oiseaux et les poissons.

Au-delà de l'appréhension du polymorphisme, ce TP vous permettra de vous familiariser avec la conception d'un diagramme de classe.

## Les animaux 🐒

### Liste 📝

Dans le Zoo il y a : 
- Des lions
- Des Dauphins
- Des ornithorynques

### Fonctionnalités ✨

Chaque animal dispose : 
- D'un nom
- D'un nom scientifique
- D'un genre

#### Les lions 🦁

Le lion est un mammifère.
- Le lion peut pousser un cri (rugir)
- Le lion peut manger
- Le lion peut dormir
- Le lion peut se déplacer (marcher/courir)
- Le lion peut chasser
- Le lion peut se reproduire
- Il peut accoucher

#### Les Dauphins 🐬

Le Dauphin est un mammifère marin.
- Le dauphin peut manger
- Le dauphin peut dormir
- Le dauphin peut nager
- Le dauphin peut accoucher
- Le dauphin peut pousser un cri (siffler)
- Le dauphin peut se déplacer (nager)

#### Les ornithorynques 🦆🦫🥚

L'ornithorynque est un mammifère ovipare.
- L'ornithorynque peut manger
- L'ornithorynque peut dormir
- L'ornithorynque peut pousser un cri (grogner)
- L'ornithorynque peut pondre des oeufs
- L'ornithorynque peut allaiter
- L'ornithorynque peut se déplacer (marcher/nager)

## Le Zoo 🦉

### Conception 🧠

Commencez par créer le diagramme de classe du Zoo.

### Développement 💻

- Créez une classe `Main` qui contiendra le code permettant de faire fonctionner le Zoo (voir les attendus dans la partie "Attendus")
- Créez les différentes classes d'animaux en respectant votre diagramme de classe

> Pour les fonctionnalités des animaux, vous devez utiliser des `System.out.println()` pour afficher le résultat de l'action.

> N'oubliez pas que d'un animal à l'autre, le résultat peut être différent !

### Attendus 🤓

- Créez une instance pour chaque animal
- Faites en sorte que tous les animaux mangent
- Faites en sorte que tous les animaux poussent leur cri
- Faites en sorte que tous les **ovipares** pondent des oeufs
- Faites en sorte que tous les **vivipares** accouchent

## Aides 💡

- Réfléchissez bien à la hiérarchie des classes : 
    - Quels sont les attributs communs à tous les animaux ?
    - Quels seraient les attributs spécifiques à chaque animal ?
- Demandez-vous : Quand faut-il passer par une classe, une classe abstraire ou une interface ?
- Il y a de nombreuses manières de faire, il n'y a pas de bonne ou de mauvaise réponse.

Quelques termes : 
- Ovipare : Qui pond des oeufs
- Vivipare : Qui donne naissance à des petits vivants
- Mammifère : Animal qui allaite ses petits
- Marin : Qui vit dans la mer
- Terrestre : Qui vit sur la terre

## Rendu 🔎

- Vous devrez rendre votre code sur un repository GitHub
- Dans le README, vous insérerez votre diagramme de classe
- Dans la classe `Main`, vous insérerez le code qui permet de faire fonctionner votre Zoo

### En présentiel 👁️

- Vous devrez présenter votre diagramme de classe à l'oral
