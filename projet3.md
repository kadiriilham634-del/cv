## Troisième projet – Nouvelles fonctionnalités ajoutées

Dans ce troisième projet, j’ai cherché à améliorer le jeu pour le rendre plus complet et plus agréable à utiliser.

Pour développer ce projet, je me suis appuyée sur l’IA, en particulier **Gemini**. J’ai d’abord utilisé pour générer une base de code à partir de **prompts décrivant le principe du jeu et ses règles générales**. Ensuite, j’ai repris ce travail pour **modifier la logique**, ajuster certaines fonctionnalités et adapter le jeu selon mes propres choix et préférences.

J’ai d’abord ajouté un **système de record**.  
Le jeu conserve désormais le **meilleur score**, correspondant au **nombre minimum de tentatives nécessaires pour trouver le bon nombre**. Ce record s’affiche sous le menu de difficulté et se met automatiquement à jour lorsqu’une meilleure performance est réalisée, même après avoir rechargé la page.

J’ai également fait évoluer la **logique du jeu**.  
La **plage de recherche devient dynamique** : après chaque tentative incorrecte, les valeurs minimales et maximales sont ajustées en fonction de la réponse du joueur. Cela permet de visualiser plus clairement la **zone dans laquelle chercher**, rendant les indices plus précis.

Ces différentes améliorations rendent le jeu plus **guidé**, plus **cohérent** et plus **motivant**, tout en montrant comment l’intelligence artificielle peut être utilisée comme un **outil d’aide**, complété par un travail personnel d’adaptation et d’amélioration.

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
