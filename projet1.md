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

## Diagramme de flux du projet


```mermaid
flowchart TD
    A[Début] --> B[Initialisation du jeu<br/>Nombre aléatoire 1-100<br/>7 essais]
    B --> C[Affichage de l'interface<br/>Champ + bouton]
    C --> D[L'utilisateur entre un nombre]
    D --> E{Nombre valide<br/>(1 à 100) ?}

    E -- Non --> F[Message d'erreur<br/>(pas d'essai perdu)]
    F --> D

    E -- Oui --> G[Comparaison avec<br/>le nombre à trouver]

    G --> H{Nombre correct ?}
    H -- Oui --> I[Message "Bravo"<br/>Fin du jeu]

    H -- Non --> J[Indication<br/>"Plus" ou "Moins"]
    J --> K{Essais restants ?}

    K -- Oui --> D
    K -- Non --> L[Message "Perdu"<br/>Fin du jeu]
