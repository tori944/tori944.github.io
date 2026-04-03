---
title: "Pixel Games"
---

# Pixel Games

Vous trouverez dans cet article la réalisation de trois jeux en python avec le module intégré <a href="https://docs.python.org/3.15/library/tkinter.html" target="_blank">Tkinter</a>. Ce dernier permet de créer des interfaces graphiques. Nous utiliserons principalement le widget canvas permettant de dessiner et d'écrire.

# Création des jeux

## 1 : Jeu de la vie

### Introduction

Le jeu de la vie à été créé par le mathématicien John Horton Conway en 1970.
Il s'agit d'une **simulation** la plus simple possible de cellules mortes ou vivantes.

Sur un plan en 2 dimensions théoriquement infini, nous avons deux règles :
- une **cellule morte** devient vivante si elle possède 3 voisines vivantes
- une **cellule vivante** reste vivante si elle possède 2 ou 3 voisines vivantes, sinon elle meurt

Ce programme, fonctionnant par génération, fait partie de la catégorie des jeux à 0 joueur, même si nous pouvons néanmoins interagir avec les cellules.

### Réalisation

Tout le projet s'articule autour de la **classe Cellule**. Cette dernière permet de créer des objets cellule représentées par des rectangles pouvant passés de l'état 0 (mort) à l'état 1 (vivant) selon les lois vues précédemment.

Un premier fichier permet d'initialiser la fenêtre, le canvas et différentes variables comme le nombre de colonnes de cellules souhaité. 

Un dernier fichier (noté main.py) a pour rôle de créer tous les objets cellule dans le canvas, créer les différents boutons de la fenêtre ainsi que leur fonction associée. C'est ce dernier programme que nous devons exécuter pour faire tourner notre jeu.

{{<button href="https://github.com/tori944/Jeu-de-la-vie">}}Voir le code sur GitHub{{</button>}}

Image de la fenêtre de jeu : 
![Mon Jeu de la Vie](../../../image/JdlV.png "mon jeu de la vie")
_source : personnelle_


## 2 : Démineur

### Introduction
Le démineur fut **l'un des premiers jeux sur ordinateur**, voyant le jour dans les années 1960 et 1970. 

Le but du joueur face à cette grille est de **localiser les bombes** qui s'y cachent. Pour cela, les cases saines (cases vertes) lui procurent comme indice le nombre de bombes dans leurs voisines directes. Afin de les repérer et d'éviter de cliquer dessus, il est possible de placer des drapeaux (cases orange).

Lorsque toutes les cases saines sont découvertes, c'est gagné !

### Réalisation

Sur la même base que le jeu précédant. Ce programme fonctionne de même avec des objets Cellule régies par les lois propres à ce jeu.


{{<button href="https://github.com/tori944/D-mineur">}}Voir le code sur GitHub{{</button>}}

Image de la fenêtre de jeu : 
![Mon Démineur](../../../image/Dmin.png "mon démineur")
_source : personnelle_


## 3 : Snake

### Introduction

Snake est un jeu provenant de **bornes d'arcades** en 1976 développé par Gremlin Industries.

Le but de ce jeu est de contrôler un serpent pouvant grandir en avalant des pommes. Tout en faisant attention de ne pas se cogner ni aux bords de l'écran de jeu, ni à lui-même

### Réalisation

Sur la même structure que les programmes précédents

{{<button href="https://github.com/tori944/Snake">}}Voir le code sur GitHub{{</button>}}

Image de la fenêtre de jeu : 
![Mon Snake](../../../image/snake.png "mon snake")
_source : personnelle_

