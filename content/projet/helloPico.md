---
weight: 1
bookFlatSection: true
title: "Hello Pico"
---

# Minis programmes Pour Raspbery Pi Pico






![Le Pico](../../image/pico.jpg "le Pico")
_test de source_




L'équivalent du célèbre Hello World avec des microcontroleurs serait sans doute de faire clignoté la led integré !



## LED  

```C

int i = 0;

void setup() {

  pinMode(25, OUTPUT);
  Serial.begin(9600);

}

void loop() {

  Serial.println(i);

  analogWrite(25, 50); 
  Serial.println(" Allume");
  delay(500);

  digitalWrite(25, 0); 
  Serial.println(" Eteint");
  delay(1000);

  i++;

}

````


