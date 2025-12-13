# Le Juste Prix  
*Jeu de devinette*

## Description du projet

Au départ, je voulais simplement tester la librairie **Anime.js** afin d’animer une phrase sur une page web.  
En avançant dans le projet, j’ai finalement choisi de développer quelque chose de plus interactif : un **mini-jeu inspiré du Juste Prix**.

L’objectif était de créer un jeu simple, facile à comprendre, tout en travaillant la logique en JavaScript.

## Principe du jeu

Le joueur doit **deviner un nombre compris entre 1 et 100**.  
Il dispose de **7 tentatives maximum**.

À chaque essai, le jeu indique si le nombre proposé est **plus grand ou plus petit** que le nombre à trouver.  
Un historique permet de suivre les réponses déjà données, ainsi qu’un compteur des tentatives restantes.

## Interface

L’interface est volontairement **simple et épurée**, afin que le jeu soit rapide à comprendre et agréable à utiliser.  
Les animations sont légères et servent surtout à rendre l’expérience plus dynamique.

## Technologies utilisées

- HTML  
- CSS  
- JavaScript  
- Anime.js  

## Apports du projet

Ce projet m’a permis de mieux comprendre :
- la logique conditionnelle en JavaScript  
- la gestion des interactions utilisateur  
- l’utilisation d’une librairie d’animation  

## Outils utilisés

Pour réaliser ce projet, j’ai utilisé **Gemini** comme aide au démarrage, puis j’ai **apporté des modifications et des ajustements personnels** au contenu et au fonctionnement du jeu.

flowchart TD
A[Début] --> B[Initialiser le jeu<br/>- nombre aléatoire 1..100<br/>- essais = 7<br/>- historique = vide]
B --> C[Afficher l'interface<br/>champ + bouton Valider]
C --> D{L'utilisateur saisit un nombre<br/>et clique "Valider"}
D --> E{Entrée valide ?<br/>vide / pas un nombre / hors 1..100}
E -- Non --> F[Afficher message d'erreur<br/>et ne pas consommer d'essai]
F --> D

E -- Oui --> G[Enregistrer la tentative<br/>dans l'historique]
G --> H[essais = essais - 1]
H --> I{Nombre = cible ?}
I -- Oui --> J[Afficher "Bravo"<br/>bloquer les entrées]
J --> K[Proposer "Rejouer"]
K --> B

I -- Non --> L{Nombre < cible ?}
L -- Oui --> M[Afficher "C'est plus"]
L -- Non --> N[Afficher "C'est moins"]
M --> O{essais > 0 ?}
N --> O

O -- Oui --> D
O -- Non --> P[Afficher "Perdu"<br/>révéler la cible]
P --> K
