## Troisième projet – Nouvelles fonctionnalités ajoutées

Dans ce troisième projet, j’ai apporté plusieurs améliorations au jeu afin de le rendre plus complet et plus interactif.

Tout d’abord, j’ai ajouté un **système de record**.  
Le jeu mémorise désormais le **meilleur score**, c’est-à-dire le **nombre minimum de tentatives utilisées pour trouver le bon nombre**.  
Ce record s’affiche sous le menu de difficulté et se met automatiquement à jour lorsqu’une meilleure performance est réalisée, même après avoir rechargé la page.

Ensuite, j’ai fait évoluer la **logique du jeu**.  
La **plage de recherche devient dynamique** : après chaque tentative incorrecte, les bornes minimales et maximales sont ajustées en fonction de la réponse donnée.  
Le joueur voit ainsi clairement la **nouvelle zone dans laquelle chercher**, ce qui rend les indices plus précis.

Ces ajouts permettent de rendre le jeu plus **guidé**, plus **intelligent** et plus **motivant** pour l’utilisateur.

## Diagramme de flux 

```mermaid
flowchart TD
    A[Début] --> B[Choix de la difficulté]
    B --> C[Démarrage du jeu]
    C --> D[Saisie du nombre]

    D --> E{Nombre correct ?}

    E -- Oui --> F[Victoire]
    F --> G[Calcul du score]
    G --> H{Nouveau record ?}
    H -- Oui --> I[Enregistrement du record]
    H -- Non --> J[Fin du jeu]
    I --> J

    E -- Non --> K{Tentatives restantes ?}
    K -- Non --> L[Défaite]
    K -- Oui --> M[Indice Plus ou Moins]
    M --> N[Mise à jour des bornes min / max]
    N --> D
