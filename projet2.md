Dans cette version, le jeu n’est plus limité à un seul mode. J’ai ajouté un menu qui
permet de choisir entre trois niveaux de difficulté avec des plages de nombres et 
des nombres de tentatives différents.
L’interface change ensuite automatiquement le nombre secret, les essais
possibles et la limite des valeurs s’adaptent au niveau choisi.
J’ai aussi amélioré l’affichage, ajouté un bouton pour rejouer en revenant au choix
de difficulté, et rendu la saisie plus claire en indiquant les erreurs et la bonne plage de nombres.

## Diagramme de flux 

```mermaid
flowchart TD
  A[Debut] --> B[Menu difficulte]
  B --> C{Choix difficulte}

  C --> D[Initialisation du niveau]
  D --> E[Nombre secret genere]
  E --> F[Saisie du nombre]

  F --> G{Correct}

  G -- Oui --> H[Bravo]
  H --> I[Rejouer]
  I --> B

  G -- Non --> J[Message erreur ou indice]
  J --> K{Essais restants}

  K -- Oui --> F
  K -- Non --> L[Perdu]
  L --> I
