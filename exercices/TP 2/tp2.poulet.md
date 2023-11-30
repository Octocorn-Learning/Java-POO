# TP 2 : Encapsulation

Votre objectif est de réaliser un programme permettant de gérer des températures.

Il doit être capable de :

- Instancier le Thermomètre avec et sans température
- Stocker une température
- Retourner la température en Celsius, Fahrenheit et Kelvin
- Modifier la température en Celsius, Fahrenheit et Kelvin

Il vous appartient de :
- Créer un diagramme de classe UML
    - Diagramme Fonctionnel
    - Diagramme Technique
- Créer la/les classes nécessaires à partir du diagramme

> Vous créerez un dépot github pour ce TP, et vous y ajouterez vos différents exercices.

> Les diagrammes de classe seront à indiquer dans le README.md du dépot !

### Contraintes 🚨

- Celsius = (Fahrenheit - 32) / 1.8
- Fahrenheit = Celsius * 1.8 + 32
- Kelvin = Celsius + 273.15

- Celsius = Kelvin - 273.15
- Fahrenheit = (Kelvin - 273.15) * 1.8 + 32
- Kelvin = (Fahrenheit - 32) / 1.8 + 273.15

### Exemples de résultats attendus 🔦

#### Exemple 1

- Température saisie : `10`
- Résultat : `10°C = 50°F = 283.15°K`
- Explication : Cf formules ci-dessus

#### Exemple 2

- Température saisie : `50`
- Résultat : `50°C = 122°F = 323.15°K`
- Explication : Cf formules ci-dessus

### Indices 💡

- Définissez le type de température par défaut
- Vous devrez créer 2 constructeurs :
    - Un constructeur avec un paramètre
    - Un constructeur sans paramètre