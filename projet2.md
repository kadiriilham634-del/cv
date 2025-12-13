## Deuxième projet – Version avec niveaux de difficulté

Dans cette deuxième version, le jeu a été amélioré et n’est plus limité à un seul mode.  
Un **menu de sélection** permet de choisir entre **trois niveaux de difficulté**.

Chaque niveau propose une **plage de nombres différente** ainsi qu’un **nombre de tentatives adapté**.  
Une fois la difficulté choisie, le jeu s’adapte automatiquement : le nombre secret change, le nombre d’essais disponibles est mis à jour et la plage de valeurs autorisées s’ajuste au niveau sélectionné.

L’interface a également été améliorée afin de rendre le jeu plus clair et plus facile à utiliser.  
Un **bouton “Rejouer”** permet de revenir au choix de la difficulté, et des **messages d’erreur** indiquent au joueur lorsque la saisie est incorrecte ou hors de la plage attendue.

Pour réaliser cette version, j’ai utilisé **Gemini** comme base de travail, puis j’ai **apporté des modifications et des ajustements personnels** au fonctionnement et à l’affichage du jeu.

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
