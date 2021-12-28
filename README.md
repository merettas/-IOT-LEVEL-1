# IOT-LEVEL-1

>I'm Meretta Suresh,second year BCA(Bachelor of Computer Applications ) student at Kristu Jyoti College of Management and Technology.

>The following are the IOT experiments and assignments I have done as part of the Kerala IOT challenge LEVEL-1

| |Experiment |
| ----------- | ----------- |
|1|HELLO WORLD LED BLINKING  |
|2| TRAFFIC LIGHT |
|3| LED CHASING EFFECT |
|4| BUTTON CONTROLLED LED |
|5| BUZZER |
|6| RGB LED |
|7| LDR LIGHT SENSOR |
|8| FLAME SENSOR |
|9| LM35 TEMPERATURE SENSOR |
|10| IR REMOTE CONTROL USING TSOP |
|11| POTENTIOMETER ANALOG VALUE READING |
|12| 7 SEGMENT DISPLAY|

| |Assignments |
| ----------- | ----------- |
|1| AUTOMATIC NIGHT LAMP |
|2| DIGITAL DICE USING LEDS|

## EXPERIMENT 1 - HELLO WORLD LED BLINKING

### Components required

- Arduino UNO Board
- USB Cable
- LED
- 220 ohm Resistor
- breadboard
- Jumper wires
  
  ![blinking led](https://user-images.githubusercontent.com/84284079/147500159-a9c0af20-2f3c-400d-8824-0d03484146c4.PNG)

### CODE


  void setup() 
  
  {
  
  pinMode(LED_BUILTIN, OUTPUT);
  
  }
  
  void loop()
  
  {
  
  digitalWrite(LED_BUILTIN, HIGH);
  
  delay(1000); // Wait for 1000 millisecond(s)
  
  digitalWrite(LED_BUILTIN, LOW);
  
  delay(1000); // Wait for 1000 millisecond(s)
  
  } 

  
## EXPERIMENT 2 - TRAFFIC LIGHT

### Components required

- Arduino UNO Board
- USB Cable
- LED-red,yellow,green
- 220 ohm Resistor * 3
- breadboard
- Jumper wires

![traffic1](https://user-images.githubusercontent.com/84284079/147505602-90ab6b31-c93b-4c43-984b-95bf2b5272ef.png)

### CODE

int animationspeed = 0;

void setup()

 {

  pinMode(LED_BUILTIN, OUTPUT);
  
  pinMode(12, OUTPUT);
  
  pinMode(11, OUTPUT);
  
 }

void loop()

 {

  animationspeed = 400;
  
  digitalWrite(LED_BUILTIN, HIGH);
  
  delay(animationspeed); // Wait for animationspeed millisecond(s)
  
  digitalWrite(LED_BUILTIN, LOW);
  
  delay(animationspeed); // Wait for animationspeed millisecond(s)
  
  digitalWrite(12, HIGH);
  
  delay(animationspeed); // Wait for animationspeed millisecond(s)
  
  digitalWrite(12, LOW);
  
  delay(animationspeed); // Wait for animationspeed millisecond(s)
  
  digitalWrite(11, HIGH);
  
  delay(animationspeed); // Wait for animationspeed millisecond(s)
  
  digitalWrite(11, LOW);
  
 }

## EXPERIMENT 3 - LED CHASING EFFECT

### Components required

- Arduino UNO Board
- USB Cable
- LED * 6
- 220 ohm Resistor * 6
- breadboard
- Jumper wires

![chasing](https://user-images.githubusercontent.com/84284079/147505944-6bc3f535-61e5-4df7-a96f-fe704ad71753.png)

### CODE

int BASE = 2; // the I/O pin for the first LED

int NUM = 6; // number of LEDs

void setup()

{

   for (int i = BASE; i <BASE + NUM; i ++) 
   
   {
   
     pinMode(i, OUTPUT); // set I/O pins as output
     
   }
   
}

void loop()

{

   for (int i = BASE; i <=BASE + NUM; i ++) 
   
   {
   
     digitalWrite(i, LOW); // set I/O pins as “low”, turn off LEDs one by one.
     
     delay(100); // delay
     
   }
   
   for (int i = BASE; i <BASE + NUM; i ++) 
   
   {
   
     digitalWrite(i, HIGH); // set I/O pins as “high”, turn on LEDs one by one
     
     delay(100); // delay
     
   }  
   
}

## EXPERIMENT 4 - BUTTON CONTROOLED LED

### Components required

- Arduino UNO Board
- Button switch
- USB Cable
- Red m5 LED
- 220 ohm Resistor
- 10 K ohm Resistor
- breadboard
- Jumper wires

![button controlled led](https://user-images.githubusercontent.com/84284079/147506157-771631ef-a06e-407c-850b-57af00a70e07.png)

### CODE

int buttonstate = 0;

void setup()

{

  pinMode(2, INPUT);
  
  pinMode(LED_BUILTIN, OUTPUT);
  
}

void loop()

{

  buttonstate = digitalRead(2);
  
  if (buttonstate == HIGH) 
  
  {
  
    digitalWrite(LED_BUILTIN, HIGH);
    
  } 
  
  else
  
  {
  
    digitalWrite(LED_BUILTIN, LOW);
    
  }
  
  delay(10); // Delay a little bit to improve simulation performance
  
}

## EXPERIMENT 5 - BUZZER

### Components required

- Arduino UNO Board
- Buzzer
- USB Cable
- breadboard
- Jumper wires

![buzzer](https://user-images.githubusercontent.com/84284079/147506574-65a8bf62-10e2-4bce-9c91-05dcec7b73f7.png)

### CODE

void setup() 

{ 

  pinMode(8, OUTPUT);
  
} 

void loop() 

{

  digitalWrite(8, HIGH);
  
  delay(1000);
  
  digitalWrite(8, LOW);
  
  delay(1000); 
  
}


## EXPERIMENT 6 - RGB LED

### Components required

- Arduino UNO Board
- USB Cable
- RGB LED
- 220 ohm Resistor * 3
- breadboard
- Jumper wires

![rgb led](https://user-images.githubusercontent.com/84284079/147506588-2ea9e417-368a-4d60-899e-598ba4d3cdc4.png)

### CODE

int red = 11;

int blue =10;

int green =9;

int val;

void setup()

{

  pinMode(red, OUTPUT);
  
  pinMode(blue, OUTPUT);
  
  pinMode(green, OUTPUT);
  
  Serial.begin(9600);
  
}

void loop() 

{

for(val=255; val>0; val--)

  {
  
   analogWrite(11, val);
   
   analogWrite(10, 255-val);
   
   analogWrite(9, 128-val);
   
   delay(10); 
   
  }
  
for(val=0; val<255; val++)

  {
  
   analogWrite(11, val);
   
   analogWrite(10, 255-val);
   
   analogWrite(9, 128-val);
   
   delay(10); 
   
  }
  
 Serial.println(val, DEC);
 
}


## EXPERIMENT 7 - LDR LIGHT SENSOR

### Components required

- Arduino UNO Board
- USB Cable
- Photo Resistor
- Red LED
- 220 ohm Resistor
- 10 K ohm Resistor
- breadboard
- Jumper wires

![ldr lght sensor](https://user-images.githubusercontent.com/84284079/147506619-e2fe68e5-f898-40c4-8c53-6403ad032ac3.png)

### CODE

int potpin=0;

int ledpin=11;

int val=0;

void setup()

{

pinMode(ledpin,OUTPUT);

Serial.begin(9600);

}

void loop()

{

val=analogRead(potpin);

Serial.println(val);

analogWrite(ledpin,val/4);

delay(10);

}


## EXPERIMENT 8 - FLAME SENSOR

### Components required

- Arduino UNO Board
- USB Cable
- Flame Sensor
- Buzzer
- 10 k ohm Resistor
- breadboard
- Jumper wires

![flame](https://user-images.githubusercontent.com/84284079/147506649-6922bd2d-b75f-4fec-b196-d4fb1647a645.png)

### CODE

const int buzzerPin = 12;

const int flamePin = 11;

int Flame = HIGH;

void setup() 

{

  pinMode(buzzerPin, OUTPUT);
  
  pinMode(flamePin, INPUT);
  
  Serial.begin(9600);
  
}

void loop() 

{

  Flame = digitalRead(flamePin);
  
  if (Flame== LOW)
  
  {
  
    Serial.println("Fire!!!");
    
    digitalWrite(buzzerPin, HIGH);
    
  }
  
  else
  
  {
  
    Serial.println("No worries");
    
    digitalWrite(buzzerPin, LOW);
    
  }
  
}

## EXPERIMENT 9-LM35 TEMPERATURE SENSOR

### Components required

- Arduino UNO Board
- LM35
- USB Cable
- breadboard
- Jumper wires

![lm35 2](https://user-images.githubusercontent.com/84284079/147506686-0379dfe7-3b5f-4ac6-a113-402cfab483d1.png)

![lm 35 3](https://user-images.githubusercontent.com/84284079/147506696-780f6d62-fe00-44c4-9382-beab48f14b3b.png)

### CODE

int potPin = 0; 

void setup() 

{

Serial.begin(9600);

}

void loop()

{

int val;

int dat;

val=analogRead(0);

dat=(125*val)>>8;

Serial.print("Tep");

Serial.print(dat);

Serial.println("C");

delay(500);

## EXPERIMENT 10 - IR REMOTE CONTROL USING TSOP

### Components required

- Arduino UNO Board
- USB Cable
- IR Remote Controller
- IR receiver
- LED * 6
- 220 ohm Resistor * 6
- breadboard
- Jumper wires

![ir remote](https://user-images.githubusercontent.com/84284079/147506741-9e8d4efd-a9de-424e-b0ba-d58ec39058da.png)

### CODE

int potPin = 0; 

void setup()

{

Serial.begin(9600);

}

void loop()

{

int val;

int dat;

val=analogRead(0);

dat=(125*val)>>8;

Serial.print("Tep");

Serial.print(dat);

Serial.println("C");

delay(500);    

Ir remote

#include <IRremote.h>

int RECV_PIN = 11;

int LED2 = 3;

int LED3 = 4;

int LED4 = 5;

int LED5 = 6;

int LED6 = 7;

long on1  = 0x00FF6897;

long off1 = 0x00FF9867;

long on2 = 0x00FFB04F;

long off2 = 0x00FF30CF;

long on3 = 0x00FF18E7;

long off3 = 0x00FF7A85;

long on4 = 0x00FF10EF;

long off4 = 0x00FF38C7;

long on5 = 0x00FF5AA5;

long off5 = 0x00FF42BD;

long on6 = 0x00FF4AB5;

long off6 = 0x00FF52AD;

IRrecv irrecv(RECV_PIN);

decode_results results;

void dump(decode_results *results)

{

  int count = results->rawlen;
  
  if (results->decode_type == UNKNOWN) 
  
    {
    
     Serial.println("Could not decode message");
     
    } 
    
  else 
  
   {
   
    if (results->decode_type == NEC) 
    
      {
      
       Serial.print("Decoded NEC: ");
       
      } 
      
    else if (results->decode_type == SONY) 
    
      {
      
       Serial.print("Decoded SONY: ");
       
      } 
      
    else if (results->decode_type == RC5) 
    
      {
      
       Serial.print("Decoded RC5: ");
       
      } 
      
    else if (results->decode_type == RC6) 
    
      {
      
       Serial.print("Decoded RC6: ");
       
      }
      
     Serial.print(results->value, HEX);
     
     Serial.print(" (");
     
     Serial.print(results->bits, DEC);
     
     Serial.println(" bits)");
     
     }
     
     Serial.print("Raw (");
     
     Serial.print(count, DEC);
     
     Serial.print("): ");
     
 for (int i = 0; i < count; i++) 
 
     {
     
      if ((i % 2) == 1) {
      
      Serial.print(results->rawbuf[i]*USECPERTICK, DEC);
      
     } 
     
    else  
    
     {
     
      Serial.print(-(int)results->rawbuf[i]*USECPERTICK, DEC);
      
     }
     
    Serial.print(" ");
    
     }
     
      Serial.println("");
      
     }
     
void setup()

 {
 
  pinMode(RECV_PIN, INPUT);   
  
  pinMode(LED1, OUTPUT);
  
  pinMode(LED2, OUTPUT);
  
  pinMode(LED3, OUTPUT);
  
  pinMode(LED4, OUTPUT);
  
  pinMode(LED5, OUTPUT);
  
  pinMode(LED6, OUTPUT);  
  
  pinMode(13, OUTPUT);
  
  Serial.begin(9600);
  
   irrecv.enableIRIn(); // Start the receiver
   
 }
 
int on = 0;

unsigned long last = millis();

void loop() 

{

  if (irrecv.decode(&results)) 
  
   {
   
    if (millis() - last > 250) 
    
      {
      
       on = !on;
       
       digitalWrite(13, on ? HIGH : LOW);
       
       dump(&results);
       
      }
      
    if (results.value == on1 )
    
       digitalWrite(LED1, HIGH);
       
    if (results.value == off1 )
    
       digitalWrite(LED1, LOW); 
       
    if (results.value == on2 )
    
       digitalWrite(LED2, HIGH);
       
    if (results.value == off2 )
    
       digitalWrite(LED2, LOW); 
       
    if (results.value == on3 )
    
       digitalWrite(LED3, HIGH);
       
    if (results.value == off3 )
    
       digitalWrite(LED3, LOW);
       
    if (results.value == on4 )
    
       digitalWrite(LED4, HIGH);
       
    if (results.value == off4 )
    
       digitalWrite(LED4, LOW); 
       
    if (results.value == on5 )
    
       digitalWrite(LED5, HIGH);
       
    if (results.value == off5 )
    
     digitalWrite(LED5, LOW); 
     
    if (results.value == on6 )
    
       digitalWrite(LED6, HIGH);
       
    if (results.value == off6 )
    
       digitalWrite(LED6, LOW);    
       
    last = millis();      
    
    irrecv.resume(); 
    
  }
  
}

}

## EXPERIMENT 11 - POTENTIOMETER ANALOG VALUE READING

### Components required

- Arduino UNO Board
- USB Cable
- 10K Potentiometer
- breadboard
- Jumper wires

![potentiometer](https://user-images.githubusercontent.com/84284079/147506770-21c8a2d7-faeb-4f3c-b8ec-d4dfc8f734b4.png)

### CODE

int potpin=0;

int ledpin=13;

int val=0;//

void setup()

{

pinMode(ledpin,OUTPUT);

Serial.begin(9600);

}

void loop()

{

digitalWrite(ledpin,HIGH);

delay(50);

digitalWrite(ledpin,LOW);

delay(50);

val=analogRead(potpin);

Serial.println(val);

}

## EXPERIMENT 12- 7 SEGMENT DISPLAY

### Components required

- Arduino UNO Board
- USB Cable
- 1 Digit LED Segment Display
- 220 ohm Resistor * 8
- breadboard
- Jumper wires

![7 segment](https://user-images.githubusercontent.com/84284079/147506788-7b9c84a1-bd54-4f72-b635-b0b3e91bb26f.png)

### CODE

int a=7;

int b=6;

int c=5;

int d=10;

int e=11;

int f=8;

int g=9;

int dp=4;

void digital_0(void) 

{

unsigned char j;

digitalWrite(a,HIGH);

digitalWrite(b,HIGH);

digitalWrite(c,HIGH);

digitalWrite(d,HIGH);

digitalWrite(e,HIGH);

digitalWrite(f,HIGH);

digitalWrite(g,LOW);

digitalWrite(dp,LOW);

}

void digital_1(void) 

{

unsigned char j;

digitalWrite(c,HIGH);

digitalWrite(b,HIGH);

for(j=7;j<=11;j++)

digitalWrite(j,LOW);

digitalWrite(dp,LOW);

}

void digital_2(void) 

{

unsigned char j;

digitalWrite(b,HIGH);

digitalWrite(a,HIGH);

for(j=9;j<=11;j++)

digitalWrite(j,HIGH);

digitalWrite(dp,LOW);

digitalWrite(c,LOW);

digitalWrite(f,LOW);

}

void digital_3(void) 

{

digitalWrite(g,HIGH);

digitalWrite(a,HIGH);

digitalWrite(b,HIGH);

digitalWrite(c,HIGH);

digitalWrite(d,HIGH);

digitalWrite(dp,LOW);

digitalWrite(f,LOW);

digitalWrite(e,LOW);

}

void digital_4(void) 

{

digitalWrite(c,HIGH);

digitalWrite(b,HIGH);

digitalWrite(f,HIGH);

digitalWrite(g,HIGH);

digitalWrite(dp,LOW);

digitalWrite(a,LOW);

digitalWrite(e,LOW);

digitalWrite(d,LOW);

}

void digital_5(void) 

{

unsigned char j;

digitalWrite(a,HIGH);

digitalWrite(b, LOW);

digitalWrite(c,HIGH);

digitalWrite(d,HIGH);

digitalWrite(e, LOW);

digitalWrite(f,HIGH);

digitalWrite(g,HIGH);

digitalWrite(dp,LOW);

}

void digital_6(void) 

{

unsigned char j;

for(j=7;j<=11;j++)

digitalWrite(j,HIGH);

digitalWrite(c,HIGH);

digitalWrite(dp,LOW);

digitalWrite(b,LOW);

}

void digital_7(void) 

{

unsigned char j;

for(j=5;j<=7;j++)

digitalWrite(j,HIGH);

digitalWrite(dp,LOW);

for(j=8;j<=11;j++)

digitalWrite(j,LOW);

}

void digital_8(void) 

{

unsigned char j;

for(j=5;j<=11;j++)

digitalWrite(j,HIGH);

digitalWrite(dp,LOW);

}

void digital_9(void) 

{

unsigned char j;

digitalWrite(a,HIGH);

digitalWrite(b,HIGH);

digitalWrite(c,HIGH);

digitalWrite(d,HIGH);

digitalWrite(e, LOW);

digitalWrite(f,HIGH);

digitalWrite(g,HIGH);

digitalWrite(dp,LOW);

}

void setup()

{

int i;// set variable

for(i=4;i<=11;i++)

pinMode(i,OUTPUT);

}

void loop()

{

while(1)

{

digital_0();

delay(1000);

digital_1();

delay(1000);

digital_2();

delay(1000); 

digital_3();

delay(1000);

digital_4();

delay(1000); 

digital_5();

delay(1000); 

digital_6();

delay(1000);

digital_7();

delay(1000); 

digital_8();

delay(1000); 

digital_9();

delay(1000); 

}}

## ASSIGNMENT 1- AUTOMATIC NIGHT LAMP USING LED AND LDR 

![ass 1](https://user-images.githubusercontent.com/84284079/147559669-e8bece9f-86d7-42fd-8584-61032dec66ee.png)

### CODE

void setup()

  {
  
   Serial.begin(9600);
   
   pinMode(10,OUTPUT);
   
  pinMode(A0, INPUT); 
  
  }

void loop()

  {
  
    int c=analogRead(A0);  
 
      
    if(c<500)
    
      {
      
        digitalWrite(10,LOW);
        
      }
    
    else
    
      {
      
        digitalWrite(10,HIGH);
        
      }
      
}


## ASSIGNMENT 2- DIGITAL DICE USING 6 LEDS AND 1 PUSHBUTTON

![ass 2](https://user-images.githubusercontent.com/84284079/147560102-81d63cb8-4f2f-473c-9a02-92ec9ecb98a2.png)

### CODE

#define DEBUG 0


int first = 2;

int second = 3;

int third = 4;

int fourth = 5;

int fifth = 6;

int sixth = 7;


int button = 12;

int pressed = 0;

void setup()

{
 
  for (int i=first; i<=sixth; i++)
  
  {
  
    pinMode(i, OUTPUT);
    
  }
 
  pinMode(button, INPUT);
  

  randomSeed(analogRead(0));

 
  #ifdef DEBUG
  
    Serial.begin(9600);
    
  #endif

}

void buildUpTension() {
  
  for (int i=first; i<=sixth; i++)
  
  {
  
    if (i!=first)
    
    {
    
      digitalWrite(i-1, LOW);
      
    }
    
    digitalWrite(i, HIGH);
    
    delay(100);
    
  }
  
  for (int i=sixth; i>=first; i--) 
  
  {
  
    if (i!=sixth)
    
    {
    
      digitalWrite(i+1, LOW);
      
    }
    
    digitalWrite(i, HIGH);
    
    delay(100);
    
  }
  
}

void showNumber(int number)

{

  digitalWrite(first, HIGH);
  
  if (number >= 2)
  
  {
  
    digitalWrite(second, HIGH);
    
  }
  
  if (number >= 3)
  
  {
  
   digitalWrite(third, HIGH);   
    
  }
  
  if (number >= 4)
  
  {
  
    digitalWrite(fourth, HIGH);    
    
  }
  
  if (number >= 5)
  
  {
  
    digitalWrite(fifth, HIGH);   
    
  }
  
  if (number == 6) 
  
  {
  
    digitalWrite(sixth, HIGH); 
    
  }
  
}

int throwDice() {
  
  int randNumber = random(1,7);
  
  #ifdef DEBUG
  
    Serial.println(randNumber);
    
  #endif
  
  return randNumber;
  
}

void setAllLEDs(int value) 

{

  for (int i=first; i<=sixth; i++)
  
  {
  
    digitalWrite(i, value);
    
  }
  
}

void loop()

{
  
  pressed = digitalRead(button);

  if (pressed == HIGH)
  
  {
  
    setAllLEDs(LOW);
    
    buildUpTension();
    
    int thrownNumber = throwDice();
    
    showNumber(thrownNumber);
    
  } 

}


