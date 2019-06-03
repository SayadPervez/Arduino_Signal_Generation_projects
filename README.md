# _AC current generation and Amplitude Modulation using Arduino:_
___
## Intro:
#### AC current is one of the greatest gifts to mankind by Nikola Tesla. It has various applications in our modern world. Experimenting with it's characteristics is the best way to learn more about it. However it cannot be extracted from a battery as we do with DC and extracting it from the domestic powerlines is alarmingly dangerous. Here we'll discuss on how to generate AC from DC using Arduino and also generate various forms of signals using logic gates !!!
___
## DC to AC :
### Things you'll need:
#### 1) Arduino UNO
#### 2) L293D MOTOR DRIVER IC
#### 3) Breadboard
#### 4) LEDs'
___
## Circuit Diagram:
![AC_SIGNAL_GEN](https://github.com/SayadPervez/Arduino_Signal_Generation_projects/blob/master/AC_GEN.JPG?raw=true)
___
## CODE:
```C
// Default delay is set to 1000 milli seconds !
int d=1000;

void setup() {
  Serial.begin(9600);
  pinMode(8, OUTPUT);
  pinMode(9,OUTPUT);
}
// You can change the delay time using the Serial Monitor.

void loop() {
  if(Serial.available()>0)
  {
    d=(Serial.readString()).toInt();
  }
  digitalWrite(8, HIGH);  
  digitalWrite(9,LOW);
  delay(d);            
  digitalWrite(8, LOW);  
  digitalWrite(9,HIGH);
  delay(d);
}
```
___
## Briefing:
#### Connection is made according to the circuit diagram. L293D IC is a common IC used to control motors however it can also be used to generate AC current if used properly ! The yellow wires give the AC output. The frequency of AC current can be altered via Serial Monitor of the Arduino.
___
## AC OUTPUT:
![AC_O/P](https://github.com/SayadPervez/Arduino_Signal_Generation_projects/blob/master/AC%20SINE%20WAVE.jpeg?raw=true)
___
___
# Signal_Modulation using logic gates !
#### In order to modulate the signal, we'll need another AC wave out of phase with the initial AC wave. Here we'll be using another AC wave with a phase difference of π/2. For this we'll be generating another AC wave from the same Arduino pins by connecting the certain pins as follows:
#### digtialPin8 - input1(L293D) - input3(L293D)
#### digitalPin9 - input2(L293D) - input4(L293D)
![L293D_Pin_Diagram](https://github.com/SayadPervez/Arduino_Signal_Generation_projects/blob/master/L293D.JPG?raw=true)
___
#### Now make the connection as in the below picture.
![Modulation_Diagram](https://github.com/SayadPervez/Arduino_Signal_Generation_projects/blob/master/Basic%20Signal%20Gen.JPG?raw=true)
#### Replace the second IC with any logic gate you wish. Note that IC 7402(NOR) has a different pin configuration and check the input and output pins before developing.
___
## Briefing:
#### In the above picture, the power rails above and below should have a phase difference of π/2. (i.e.) The blue and yellow wires would generate AC currents with phase difference π/2. When a branch from each is taken as input and feeded to the logic gates, We would get the following wave modulations in the second Breadboard.
___
> ## *__Note: Since the frequency is constant, you won't be able to differentiate the waves by connecting the final output to a speaker.__*
___
# Result:
### Red and blue represent the AC currents created by the two branches from L293D IC and it is evident that the phase differrence is π/2.
![sine_vs_cosine](https://github.com/SayadPervez/Arduino_Signal_Generation_projects/blob/master/sine%20vs%20cosine.jpeg?raw=true)
___
## OR GATE 7432:
![OR](https://github.com/SayadPervez/Arduino_Signal_Generation_projects/blob/master/OR.png?raw=true)
___
## AND GATE 7408:
![AND](https://github.com/SayadPervez/Arduino_Signal_Generation_projects/blob/master/AND.jpeg?raw=true)
___
## COMPARISON : AND _vs_ OR
### Red (AND) is superimposed on Cyan(OR).
![ANDVSOR](https://github.com/SayadPervez/Arduino_Signal_Generation_projects/blob/master/AND%20VS%20OR.jpeg?raw=true)
___
## NOR GATE 7402
![NOR](https://github.com/SayadPervez/Arduino_Signal_Generation_projects/blob/master/NOR.jpeg?raw=true)
___
## NAND GATE 7400
![NAND](https://github.com/SayadPervez/Arduino_Signal_Generation_projects/blob/master/NAND.jpeg?raw=true)
___
## COMPARISON : NOR *vs* NAND
![NORVSNAND](https://github.com/SayadPervez/Arduino_Signal_Generation_projects/blob/master/NAND%20VS%20NOR.jpeg?raw=true)
___
___
# Developed by SAYAD PERVEZ
# Email ID : [pervez2504@gmail.com](https://accounts.google.com/signin/v2/identifier?service=mail&passive=true&rm=false&continue=https%3A%2F%2Fmail.google.com%2Fmail%2F&ss=1&scc=1&ltmpl=default&ltmplcache=2&emr=1&osid=1&flowName=GlifWebSignIn&flowEntry=ServiceLogin)
___
___
