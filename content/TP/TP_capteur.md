---
weight: 1
#bookFlatSection: true
title: "TP capteur CO2"
---

# TP capteur de CO2

## Présentation

La qualité de l’air dans une pièce peut être mesuré grâce à sa la concentration en CO2. Nous allons donc concevoir une carte électronique permettant d’indiquer ce facteur.

L’objectif est de réaliser une carte électronique indiquant lorsque le taux de CO2 à dépasser un certain seuil, ce qui déclenchera la fermeture d’un contacte.

## Principe de fonctionnement


Voici le fonctionnement du capteur (d'après les consignes):
- Un capteur de CO2 donnera une tension qui dépend du taux de CO2 dans l’air
- Cette tension sera alors comparée avec un seuil réglé par un potentiomètre.
- Quand le taux de CO2 sera supérieur au seuil, le comparateur donnera une tension positive
- Cette tension sera amplifiée par un transistor qui alimentera un relais
- Le contact du relais sera utilisé pour indiquer que le seuil de détection est atteint.
- Des leds serviront à visualiser la présence de la tension d’alimentation et l’état du capteur.
- Un régulateur de tension sera utilisé pour maintenir la tension d’alimentation à 5 V.

![](../../image/principe_fonctionnement_capteur_co2.jpg)
_Schéma de fonctionnement - source : sujet TP_

## Étude des composants

### régulateur de tension 5V
Un régulateur 5V permet de réguler une tension d’entrée (comprise entre 6.5 et 36v dans notre cas) en une tension de sortie à 5v.

{{% Columns %}}

- ![](../../image/regul5v.jpg)
_Régulateur 5v - source : personnelle_

- Ce composant possède trois broches :
    - VCC
    - GND
    - Tension de sortie

{{% /Columns %}}


### Potensiomètre
Afin de moduler le seuil de déclanchement, nous utiliserons un potentiomètre.

{{% Columns %}}

- Trois broches :
    - VCC
    - Tension de sortie
    - GND

- ![](../../image/po.jpg)
_Potentiomètre - source : personnelle_

{{% /Columns %}}
 

### Capteur de CO2
Ce capteur de gaz MQ2 renvois une tension variable en fonction du taux de CO2 ambiant.

{{% Columns %}}

- ![](../../image/capteur_gaz.jpg)
_Capteur CO2 - source : personnelle_

- 4 briches, respectivement :
    - GND
    - VCC
    - D0 (sortie digital)
    - A0 (sortie analogique)

{{% /Columns %}}


### LM 538

Nous allons utilisé un amplificateur opérationnel comme **comparateur**
{{% Columns %}}

- 8 broches :
    - VCC
    - GNC
    - 3x2 pour deux comparateurs (deux entrée et une sortie)

- ![](../../image/lm358.jpg)
_LM538 - source : personnelle_

- ![](../../image/schema538.png)
_schéma LM538 - source : alldatasheet.fr_

{{% /Columns %}}

### Transistor

Pour **amplifier** le signal à la suite du comparateur, nous utiliserons un transistor **BC237B NPN**, c’est-à-dire que le courant va du collecteur à l’émetteur.

{{% Columns %}}

- ![](../../image/schemaTransistor.png)
_Transistor - source :  alldatasheet.fr_

- ![](../../image/transistor.jpg)
_source : personnelle_

- 3 broches :
    - Emeteur
    - Base
    - Collecteur

{{% /Columns %}}

### Relais

Le relais électromagnétique permet l’ouverture ou la fermeture d’un circuit
indépendant grâce à une bobine actionnant des interrupteurs. 

{{% Columns %}}

- 8 broches :
    - VCC
    - GND
    - 3x2 pour les circuits indépendants

- ![](../../image/relais.png)
_relais - source : soselectronic.com_

- ![](../../image/schemaRelais.png)
_relais - source : soselectronic.com_

{{% /Columns %}}


### Condensateur
{{% Columns %}}

- ![](../../image/condensateur.jpg)
_source : personnelle_

- Un condensateur électrochimique de 47μF est utilisé afin
de filtrer et stabilisé la tension d’alimentation du circuit.

{{% /Columns %}}

### Leds et résistances


{{% Columns %}}

- Afin de signaler la présence ou non de tension, nous utiliserons des leds et résistances
de 4k7 et 330 ohms.

- ![](../../image/led.jpg)
_source : personnelle_

- ![](../../image/resistance.jpg)
_source : personnelle_


{{% /Columns %}}


### Diode

{{% Columns %}}

- ![](../../image/diode.jpg)
_source : personnelle_

- Une diode 1N4148 qui sera utilisé comme
diode de roue libre, c’est-à-dire qu’elle sera
reliée à la bobine du relais pour empêcher la
tension de retour.

{{% /Columns %}}


## Réalisation du circuit
Nous allons réaliser le circuit pas à pas

### Alimentation, condensateur et régulateur 5v

{{% Columns %}}

- ![](../../image/s1.png)
_schéma électrique - source : sujet TP_

- Voici le début du circuit, nous pouvons y voir l’alimentation, une pile 9V dans notre cas. A laquelle nous ajouton le condensateur ainsi que la led (avec résistance). Nous finissons cette partie par le régukateur 5v

{{% /Columns %}}

### Tension de seuil, capteur et comparateur

{{% Columns %}}

- ![](../../image/s2.png)
_schéma électrique - source : sujet TP_

- Nous y ajoutons le potenciomètre ainsi que le capteur de CO2. ces deux élments délivrerons une tention differentes qui va alors être comparer par le LM 358. Si la tension du capteur dépasse celle du potenciomètre, le comparateur délivrera un signal. 

{{% /Columns %}}

### Transmission

Ici nous avons transmis la tension en sortie du comparateur à un transistor afin que ce dernier agisse comme un interrupteur dans l’alimentation du relais.
Nous n’oublions pas la résistance avant le transistor car ce dernier ce déclenche avec une tension comprise entre 0.4 à 0.8 V. Ainsi que la diode de roue libre du relais.
A la sortie du relais, une led indique la présence de tension, tandis que les bornes de sorties sont actives.

![](../../image/s3.png)
_schéma électrique - source : sujet TP_

## Réalisation sur ordinateur

Dans le but de concevoir une carte électronique, nous commençons par modéliser le circuit avec le logiciel EAGLE.

![](../../image/s4.png)
_schéma electrique logiciel eagle- source : personnelle_

Ensuite, nous agençons les composant et créons le passage circuit imprimé à l’aide du même logiciel.

![](../../image/s5.png)
_schéma electrique logiciel eagle - source : personnelle_

## Réalisation Physique

### Création du circuit imprimé

Nous commençons par imprimé le dernier schéma du circuit sur une feuille de papier calque que nous venons positionner sur notre plaquette recouverte d’une filme de cuivre.
Une fois superposé, nous l’insérons dans une machine à UV pendant 90 secondes.

Voici deux images de la machine à UV.

{{% Columns %}}

- ![](../../image/m1.jpg)
_machine UV - source : personnelle_

- ![](../../image/m2.jpg)
_machine UV - source : personnelle_

{{% /Columns %}}

{{% Columns %}}

- Ensuite la carte passe dans une solution pour faire apparaitre le circuit.
![](../../image/cs.jpg)
_bain solution - source : personnelle_

- Et pour finir le circuit passe dans une autre machine lui apportant une solution acide.
![](../../image/cm.jpg)
_machine solution acide - source : personnelle_

{{% /Columns %}}

### Ajout des composants

Nous perforons la carte et y soudons les composants.

{{% Columns %}}

- ![](../../image/c1.jpg)
_perforation - source : personnelle_

- ![](../../image/c2.jpg)
_carte perforé - source : personnelle_

- ![](../../image/c3.jpg)
_carte composants soudés - source : personnelle_

{{% /Columns %}}

## Vérification

Afin de vérifier que la carte fonctionne bien, nous testons que le courtant sircule bien en tout point et qu’il n’y a pas de perte.

Ensuite nous testons la carte en conditions.

Résultat final : 

![](../../image/carteFinal.jpg)
_résultat final - source : personnelle_

## Conclusion

Nous avons pu réalisé un détecteur de CO2

Ce projet nous a permis de découvrir certain composant électronique ainsi que d’apprendre leur fonctionnement et utilisation dans le cadre d’un projet de détection de CO2. Cela nous a aussi permis d’en apprendre plus sur la conception de circuit imprimé.