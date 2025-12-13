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
Parfait, merci pour la photo 👍
Là on a la dernière erreur précise, et je t’explique simplement.

⸻

❌ Pourquoi ça ne s’affiche TOUJOURS pas

Cette fois, l’erreur vient de ça :

F[Message d'erreur<br/>(pas d'essai perdu)]

👉 Mermaid n’accepte pas les parenthèses ( ) dans le texte des blocs, surtout combinées avec <br/>.

Même problème ici :
	•	(pas d'essai perdu)
	•	guillemets "Bravo"
	•	accents + symboles dans certains cas

Résultat : parse error → pas de dessin.

⸻

✅ Solution sûre à 100 % (celle qui marche)

👉 On simplifie le texte dans les blocs, sans parenthèses, sans guillemets, sans phrases longues.

🔧 Copie-colle EXACTEMENT ce diagramme (et remplace l’ancien) :

## Diagramme de flux du projet

```mermaid
flowchart TD
    A[Début] --> B[Initialisation du jeu]
    B --> C[Afficher interface]
    C --> D[Saisie du nombre]
    D --> E{Nombre valide}

    E -- Non --> F[Message erreur]
    F --> D

    E -- Oui --> G[Comparer avec nombre cible]

    G --> H{Nombre correct}
    H -- Oui --> I[Bravo]
    I --> J[Fin du jeu]

    H -- Non --> K[Plus ou Moins]
    K --> L{Essais restants}

    L -- Oui --> D
    L -- Non --> M[Perdu]
