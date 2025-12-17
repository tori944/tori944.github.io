---
weight: 1
#bookFlatSection: true
title: "TP capteur CO2"
---

# TP capteur de CO2




L'objectif de ce tp est de créer un capteur de co2 qui ce déclanche à partir d'un seuil donné.

Voici le fonctionnement du capteur (d'après les consignes):
- Un capteur de CO2 donnera une tension qui dépend du taux de CO2 dans l’air
- Cette tension sera alors comparée avec un seuil réglé par un potentiomètre.
- Quand le taux de CO2 sera supérieur au seuil, le comparateur donnera une tension positive
- Cette tension sera amplifiée par un transistor qui alimentera un relais
- Le contact du relais sera utilisé pour indiquer que le seuil de détection est atteint.
- Des leds serviront à visualiser la présence de la tension d’alimentation et l’état du capteur.
- Un régulateur de tension sera utilisé pour maintenir la tension d’alimentation à 5 V.

![](../../image/principe_fonctionnement_capteur_co2.jpg)
_source : pdf consigne du tp_

## 1. Led présence de tension

Pour ce faire, nous commençons par ajouter un **régulateur de tension 5V**.

{{% Columns %}}

- ![](../../image/regul5v.jpg)
_source : personnelle_

- Ce composant e trois broches :
    - la première pour le +
    - la deuxième pour le -
    - la troisième pour la sortie de la tension ainsi régulé.




{{% /Columns %}}

 

En sortie on ajoute une résistance et une led afin de signifié que le courant passe bien.

## 2. Capteur

{{% Columns %}}

- On alimente le capteur avec la sortie du regulateur (borne vcc) sans oublier de relier la borne negative de ce dernier avec celle du circuit.

- ![](../../image/capteur_gaz.jpg)
_source : personnelle_

{{% /Columns %}}

La sortie du capteur est celle de la broche A0. C'est unne tension qui dépend du niveau de co2.

## 3. Seuil de déclanchement

Afin de modulé un seuil de déclanchement nous allons utilisé un **potentiomètre**, ce qui correspond à une resistance variable.

{{% Columns %}}

- ![](../../image/po.jpg)
_source : personnelle_

- Comme les autres composant utilisé, un potentiomètre possède trois patte : +, sortie et -.

{{% /Columns %}}



Le seuil de déclanchemant choisi sera alors une tension. Lorsque la sortie du détecteur atteint cette tention nous voulons le déclanchement du système.

## 4. Comparateur

Nous allons utilisé un amplificateur opérationnel du nom de **LM 358** pour comparer ces deux tentions. 

{{% Columns %}}

- il y a 8 broches :
    - 2 pour + et -
    - 3 * 2 pour deux comparateurs (deux entrée et une sortie)

- ![](../../image/lm358.jpg)
_source : personnelle_

{{% /Columns %}}

## 5. la suite j'ai pas compris

