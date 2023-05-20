# ASSIGNMENT 

## 1 SMART WASTE BIN :           
## [CLICK HERE](https://www.tinkercad.com/things/lJWylAqneBN-smart-waste-bin-project/editel)
## CIRCUIT DIAGRAM               ![IMAGE](https://github.com/shanibmuhammd/shanib/blob/main/img/DAY%2010.png)
## SCHIMATTIC DIAGRAM            ![IMAGE](https://github.com/shanibmuhammd/shanib/blob/main/img/DAY%2010-1.png)
## COMPONENT DIAGRAM             ![IMAGE](https://github.com/shanibmuhammd/shanib/blob/main/img/DAY%2010-2.png)
### CODE:
```
#include <Servo.h>

const int buzzer = 2;

Servo servox; 

int mapa,graus = 0,cm = 0;

bool tocarmusica = false;

long readUltrasonicDistance(int triggerPin, int echoPin)
{
  pinMode(triggerPin, OUTPUT);
  digitalWrite(triggerPin, LOW);
  delayMicroseconds(2); 
  digitalWrite(triggerPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(triggerPin, LOW);
  pinMode(echoPin, INPUT); 
  return pulseIn(echoPin, HIGH);
}

void setup()
{
  Serial.begin(9600);
  servox.attach(5);
  servox.write(0);
    
}

void loop()
{
  cm = 0.01723 * readUltrasonicDistance(9, 9);
  delay(10);
  if(cm < 20){
    servox.write(90);
    tocarmusica = true;
  }
  else if(20 < cm && cm < 60){
    mapa = map(cm, 20,60, 0, 90);
    graus = 90 - mapa;
    servox.write(graus);
  }else{
    servox.write(0); 
  }
delay(10);
  if(tocarmusica){
    tone(buzzer, 1000, 500);
    tocarmusica = false;
  }

 }
  
  
  


```
# KEYCHAIN
#### [CLICK HERE](https://www.tinkercad.com/things/1JmYgvEZtMF-keychain/edit)

