## Projet 6 – Version finale du jeu

Ce sixième projet correspond à la **version la plus aboutie du jeu**.  
Il reprend l’ensemble des fonctionnalités développées dans les versions précédentes et les consolide dans une expérience cohérente et fluide.

### Fonctionnalités présentes

- **Choix de la difficulté** avec des plages de nombres et un nombre de tentatives adaptés.
- **Bornes dynamiques** : la plage de recherche se réduit après chaque tentative incorrecte.
- **Système de record** : le meilleur score est sauvegardé et affiché automatiquement.
- **Mode clair / mode sombre** avec mémorisation du choix de l’utilisateur.
- **Barre de progression** indiquant visuellement les tentatives restantes.
- **Indices visuels et textuels** : plus / moins, froid / tiède / proche.
- **Retour sonore** : sons doux associés aux actions du joueur (tentative, indice, victoire, défaite).
- **Interface améliorée** : messages clairs, historique lisible et navigation fluide.

Cette version finale met l’accent sur l’**expérience utilisateur**, en combinant logique de jeu, clarté visuelle et feedback sonore, tout en restant simple à comprendre et à utiliser.

Pour cette dernière version, j’ai utilisé l’IA **Gemini** comme point de départ, notamment pour réfléchir au **visuel de l’interface**. J’ai ensuite retravaillé l’ensemble du jeu, en ajustant la logique, les fonctionnalités et l’apparence, afin que le résultat final corresponde pleinement à mes choix et à ma vision du projet.


## Diagramme de flux – Projet 6

```mermaid
flowchart TD
  A[Debut] --> B[Choix difficulte]
  B --> C[Initialisation du jeu]
  C --> D[Saisie du nombre]

  D --> E{Correct}

  E -- Oui --> F[Victoire + son]
  F --> G[Record / Rejouer]

  E -- Non --> H[Indice visuel + son]
  H --> I[Tentatives restantes ?]

  I -- Oui --> D
  I -- Non --> J[Defaite + son]
  J --> G
