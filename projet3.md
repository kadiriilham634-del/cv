Dans ce troisième test, j’ai ajouté une nouvelle fonctionnalité : le jeu garde
maintenant en mémoire le meilleur score, c’est-à-dire le nombre minimum de
tentatives utilisées pour trouver le bon nombre. Ce record s’affiche sous le menu
de difficulté et se met à jour automatiquement quand on fait mieux qu’avant.
J’ai aussi fait évoluer la logique du jeu : la plage de recherche se réduit au fur et à
mesure des essais. Quand on se trompe, le jeu ajuste les bornes (min et max) et
affiche clairement la nouvelle zone dans laquelle chercher, ce qui rend les indices
plus précis et la partie plus guidée.
