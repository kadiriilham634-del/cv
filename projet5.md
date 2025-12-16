## Projet 5 – Version avec sons 
Dans ce projet 5, j’ai repris la version précédente du jeu et j’ai ajouté une amélioration principale : **des sons** pour rendre l’expérience plus vivante.

### Ce que j’ai ajouté

- **Sons intégrés** : j’ai ajouté des bips et petites mélodies directement en JavaScript grâce à la **Web Audio API** (donc sans fichier audio externe).
- **Sons selon les actions** :
  - un petit son lors du clic sur “Deviner”,
  - un son différent selon l’indice (**froid / tiède / proche**),
  - une petite séquence sonore pour la **victoire**,
  - une autre séquence sonore pour la **défaite**.

### Ce qui est conservé

- choix de la difficulté,
- bornes dynamiques (plage qui se resserre),
- record sauvegardé,
- mode clair / mode sombre,
- barre de progression,
- historique des tentatives et feedback visuel.

L’objectif de cette version était d’améliorer l’ambiance du jeu et de donner un retour plus immédiat au joueur grâce au son.

Pour cette partie du projet, je me suis appuyée sur l'IA, **Claude** afin de m’aider à concevoir et structurer l’intégration sonore. 

## Diagramme de flux 

```mermaid
flowchart TD
  A[Debut] --> B[Choix difficulte]
  B --> C[Demarrage du jeu]
  C --> D[Saisie du nombre]
  D --> E[Son]

  E --> F{Correct}

  F -- Oui --> G[Victoire]
  G --> H[Rejouer]

  F -- Non --> I[Indice + son]
  I --> D
