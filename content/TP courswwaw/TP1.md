---
weight: 1
#bookFlatSection: true
title: "TP_1"
---

# TP 1

> [!DANGER]
> **◑﹏◐**  
> Cette page est en constructions,
> les programmes sont à remanier

{{< badge style="success" title="TP" value="Beginner" >}}


## Exercice 2


Le nombre de clic sur un bouton est retranscrit en binaire sur 3 leds

```C

  int compt; // nm clic btn
  int led1;
  int led2;
  int led3;

void setup() {

  Serial.begin(9600); //afin de pouvoir aficher dans le terminal

  pinMode(2, INPUT);
  
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  
}

void loop() {
  
  if (digitalRead(2) == HIGH){    // si btn appuyé
    compt++;                      // compt +1
    delay(500);                   // afin de ne pas prendre en compt le rebon
    if (compt == 8){compt = 0;}   // si compt arrive à 8, on repasse à 0 car on a 3 leds  
    Serial.print(compt);          // écrit dans le terminal l'état de la var compt
  }


  // convertion de la base 10 en base 2 pour les leds

    led3 = compt%2;
    led2 = (compt/2)%2;
    led1 = ((compt/2)/2)%2;


   // affichage led 

  if (led1 == 1){
    digitalWrite(3, HIGH);
  }else{
    digitalWrite(3, LOW);
  }

  if (led2 == 1){
    digitalWrite(4, HIGH);
  }else{
    digitalWrite(4, LOW);
  }

  if (led3 == 1){
    digitalWrite(5, HIGH);
  }else{
    digitalWrite(5, LOW);
  }

}

```




## Exercice 3

*pas fini* \
-> faire un schéma


```C

int temps;
int interval=3000;

void setup() {
  pinMode(2, INPUT);
  pinMode(3, OUTPUT);

}

void loop() {
  
  if (digitalRead(2) == HIGH){
    temps=millis();
    while( millis()<= (temps+interval)){
        digitalWrite(3, HIGH);
        delay(100);
        digitalWrite(3, LOW);
        delay(100);
    }
  }



  if (digitalRead(2) == HIGH){
    temps=millis();
    while( millis()<= (temps+interval)){
        digitalWrite(3, HIGH);
        delay(500);
        digitalWrite(3, LOW);
        delay(100);
    }
  }
}

```

## Exercice 4 🐛

Chenillard sur 4 LED 

```C

int i = 2;

void setup() {
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);

}
void loop() {

  digitalWrite(i, HIGH);
  delay(200);
  digitalWrite(i, LOW);

  i++;  

  if (i == 6){i = 2;}

}

```

## Exercice 5 

⚡🐛🚜\
Chenillard aller-retour qui accélère


```C

int i = 2;              // pour le nom de la pin
bool sens = true;       // le sens, si on ajoute ou retir 1 au nom de la pin      
int temps = 500;        // delay d'attente pour aller de plus en plus vite  
int compteur = 0;       // pour le nb d'itération

void setup() {
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);

}
void loop() {

  digitalWrite(i, HIGH);    // allumé
  delay(temps);             // pause
  digitalWrite(i, LOW);     // éteint


  if (sens == true){                //
    i++;                            // pour
    if (i == 5){sens = false;}      // gérer
  }else{                            // le
    i--;                            // sens
    if (i == 2){sens = true;}       //
  }                                 //

  temps = temps - 10; 

  if (temps <= 50){ 
    temps = 500;
  }

}

```


## Exercice 6

Vraiment la consigne est pas claire, ça ce vois que le gars qui a écrit ça a galéré\
Donc on va imporvisé avec un truc qui me semble cohérent\
Au programme ça sera donc chenillard qui change de sens avec le boutton\
¯\\_(ツ)_/¯

```C

int i = 2;
bool sens = true;

void setup() {

  pinMode(1, INPUT);
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);

}
void loop() {

  digitalWrite(i, HIGH);
  delay(500);
  digitalWrite(i, LOW);

  if (digitalRead(2) == HIGH){
    sens = !sens;
  }
  
  if (sens == true){
    i++;
    if (i == 6){i = 2;}
  }else{
    i--;
    if (i == 1){i = 5;}
  }
  
}

```


## Exercice 7

Ok là ça devient un peu plus rogolo, on s'attaque aux fonctions logiques
c'est à dire qu'on a :\
- 3 LED, respectivement les résultats de AND, OR, XOR 
- 2 boutons pour les variables binaires

petits tableau récapitulatif de toute ces belles fonctions :
(oui même si tout le monde les connais)

{{% columns %}}
- AND
  
  |a|b|r|
  |-|-|-|
  |0|0|0|
  |0|1|0|
  |1|1|1|
  |1|0|0|

- OR
  
  |a|b|r|
  |-|-|-|
  |0|0|0|
  |0|1|1|
  |1|1|1|
  |1|0|1|

- NOR

  |a|b|r|
  |-|-|-|
  |0|0|0|
  |0|1|1|
  |1|1|0|
  |1|0|1|

{{% /columns %}}


```C
Bientôt disponible

```

