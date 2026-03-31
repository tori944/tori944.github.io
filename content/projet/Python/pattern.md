---
title: "Dynamique des Patterns"
---

# Dynamique des Patterns

Voici un projet en python aillant pour but de pavé un espace avec des patterns définis et certaines règles d'agencements

Ce projet est inspiré de <a href="https://github.com/mxgmn/WaveFunctionCollapse?tab=readme-ov-file" target="_blank">celui-ci</a>

{{<button href="https://github.com/tori944/La-Dynamique-des-Patterns">}}Voir mon projet sur GitHub{{</button>}}


Dans mon cas j'ai repris la base de la matrice de cellule des projets de <a href="../mespixelgames">Pixel Games</a>. Cela me permet de pouvoir générer des motifs plus facilement. 
Ces motifs sont formés comme un puzzle avec des tuiles définies à l'avance.

![patterns](../../../image/patterns.png "les patterns")
_source : personnelle_

Je définie ensuite où est ce que dans mon tableau les tuiles peuvent être dessiné. La cellule centrale portera les données du motif.

Ensuite pour pouvoir dessiné une nouvelle tuile, j'interroge les voisines directes et choisie au hasard une qui correspond.

Ce programme nous donne une image comme celle-ci :

![patterns](../../../image/tableauPatterns.png "tableau avec patternes")
_source : personnelle_

Nous pouvons voir ici la continuité du motif.

Les commandes de l'utilisateur vis à vis du programme sont : 
- __clic droit__ : pour placer un motif au hasard 
- __clic gauche__ : pour propager le motif à partir de la case choisie

Les cellules bleues représentent les centres des différentes cases ou un motif peut être dessiné.