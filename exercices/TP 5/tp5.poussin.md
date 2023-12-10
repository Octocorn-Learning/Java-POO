## Exercice

### Partie 1

Créer une factory qui permet d'adopter des animaux.

- Lorsque j'adopte un chien, il aboie
- Lorsque j'adopte un chat, il miaule

#### Aides

- Réfléchissez aux noms des classes et des interfaces
    - Pensez métier, et non technique !    
- Utilisez une classe abstraite pour la factory.
    - Pensez encapsulation : d'un point de vue extérieur, on ne doit pas savoir comment est créé l'animal !
    - Tout ce qu'on veut faire, c'est adopter un animal !
- Utilisez une interface pour les animaux
    - Tous vos animaux doivent implémenter cette interface
    - Dans le contrat, ils auront tous une méthode commune !

### Partie 2

Ajoutez un nouvel animal : un perroquet.

- Lorsque j'adopte un perroquet, il dit "Polly want a cracker !"

#### Aides

- Si vous avez bien fait la partie 1, vous n'avez rien à changer dans votre code !