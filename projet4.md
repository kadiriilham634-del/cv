## Projet 4 – (améliorations interface et expérience utilisateur)

Dans ce projet 4, le jeu a continué d’évoluer à partir des versions précédentes.  

### Éléments ajoutés

- **Mode clair / mode sombre** : ajout d’un bouton permettant de changer le thème du jeu, avec mémorisation du choix pour les prochaines utilisations.
- **Barre de progression** : affichage visuel du nombre de tentatives restantes afin que le joueur puisse mieux suivre son avancée.
- **Indices de proximité** : en plus des indications “Plus” ou “Moins”, le jeu indique si le joueur est **froid, tiède ou très proche** du nombre à trouver.
- **Feedback visuel amélioré** : les messages et les couleurs changent en fonction de la situation (erreur, proximité, victoire ou défaite), ce qui rend le jeu plus lisible.
- **Historique enrichi** : les propositions du joueur sont affichées de manière plus claire, avec une mise en valeur des réponses.
- **Gestion du record conservée** : le meilleur score reste affiché et peut être amélioré au fil des parties.

Ces ajouts permettent de tester une expérience de jeu plus complète, plus guidée et plus intuitive.

### Outils utilisés

Pour ce projet, je me suis aidée de **Claude** et de **Gemini** comme outils de support, puis j’ai **retravaillé, modifié et adapté** le contenu et le fonctionnement du jeu personnellement.

## Diagramme de flux 

```mermaid
flowchart TD
  A[Debut] --> B[Choix difficulte]
  B --> C[Demarrage du jeu]
  C --> D[Saisie du nombre]

  D --> E{Correct ?}

  E -- Oui --> F[Victoire]
  F --> G[Afficher record]
  G --> H[Rejouer]

  E -- Non --> I[Indice + feedback visuel]
  I --> J[Mettre a jour tentatives]
  J --> K{Tentatives restantes ?}

  K -- Oui --> D
  K -- Non --> L[Defaite]
  L --> H
