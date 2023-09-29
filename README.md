Exp:01											Date:
LED CONTROL USING ARDUINO BOARD
Aim: To control LED Using Arduino Uno board
Apparatus:
S. No.	Apparatus	Range/Rating	Quantity
1	Universal Board		1
2	Arduino board		1
3	Led		1
4	12V Adaptor		1
5	Power jack		1
6	USB Cable		1
7	Jumper Wires		Required

Hardware Procedure:
•	LED pin is Connected to Arduino Uno pin of 2.
•	Power jack is connected to the Arduino Uno.
•	USB connector is connected to Arduino Uno to monitor.
•	Connect the 12V power supply to development board.
•	Check the output from the development board.
Software Procedure:
1.	Click on Arduino IDE
2.	Click on file
3.	Click on New
4.	Write a Program as per circuit Pin connections
5.	Click on Save
6.	Click on Verify
7.	Click on Upload the code into Arduino Uno by using USB cable.







Program:
const int led = 2;
void setup() { pinMode(led, OUTPUT);
}
void loop()
{
digitalWrite(led, HIGH); 
delay(1000); 
digitalWrite(led, LOW); 
delay(1000);
digitalWrite(led, HIGH); 
delay(1000);
digitalWrite(led, LOW); 
delay(1000);
}
Precautions:
•	Take care about given power supply (12V).
•	Jumper wires given carefully whenever given circuit connection.

RESULT: LED is successfully controlled by Arduino microcontroller Board.














Exp: 02	Date:
POTENTIOMETER AND IR SENSOR INTERFACING WITH ARDUINO
Aim: To Interface Potentiometer and IR Sensor Using Arduino Uno board
Apparatus:
S. No.	Apparatus	Range/Rating	Quantity
1	Universal Board		1
2	Arduino board		1
3	POT sensor		1
4	IR Sensor		
5	12V Adaptor		1
6	Power jack		1
7	USB Cable		1
8	Jumper Wires		Required
Hardware Procedure:
•	LED pin is Connected to Arduino Uno pin of 11 & 12.
•	POT pin is connected to the Arduino pin A1.
•	IR Sensor Pin is connected to the Arduino Pin 4.
•	Power jack is connected to the Arduino.
•	USB connector is connected to Arduino Uno to monitor.
•	Connect the 12V power supply to development board.
•	Check the output from the development board.

Software Procedure:
1.	Click on Arduino IDE
2.	Click on file
3.	Click on New
4.	Write a Program as per circuit Pin connections
5.	Click on Save
6.	Click on Verify
7.	Click on Upload the code into Arduino Uno by using USB cable.




Program:

#define LED_PIN 11
#define POTENTIOMETER_PIN A1
void setup() {
// put your setup code here, to run once:
pinMode(4,INPUT); 
pinMode(12,OUTPUT);//LED 
pinMode(LED_PIN, OUTPUT);
}
void loop() {
// put your main code here, to run repeatedly: potentiometer loop
int potentiometerValue = analogRead(POTENTIOMETER_PIN); 
int brightness = potentiometerValue / 4;
analogWrite(LED_PIN, brightness);
//ir loop
 if(digitalRead(4)==LOW){ 
digitalWrite(12,HIGH);
}
else { 
digitalWrite(12,LOW);
}
}
Precautions:
•	Take care about given power supply (12V).
•	Jumper wires given carefully whenever given circuit connection.
RESULT: Both Analog and Digital Sensors data are successfully measured by Arduino.







Exp: 03	Date:
CONTROLLING TWO ACTUATORS USING ARDUINO
Aim: To Interface Actuators Using Arduino Uno board
Apparatus:
S. No.	Apparatus	Range/Rating	Quantity
1	Universal Board		1
2	Arduino board		1
3	Realys,Battaries,Stepper Motor		2
4	12V Adaptor		1
5	Power jack		1
6	USB Cable		1
7	Jumper Wires		Required
Hardware Procedure:
•	Relay 1 pin is connected to Arduino Uno pin 9
•	Relay 2 pin is connected to Arduino Uno pin 10
•	Power jack is connected to the Arduino.
•	Attach the Bluetooth Module.
•	USB connector is connected to Arduino Uno to monitor.
•	Connect the 12V power supply to development board.
•	Check the output from the development board.
Software Procedure:
1.	Click on Arduino IDE
2.	Click on file 
3.	Click on New
4.	Write a Program as per circuit Pin connections
5.	Click on Save 
6.	Click on Verify
7.	Click on Upload the code into Arduino Uno by using USB cable.
8.	Install Serial Bluetooth Terminal app on mobile phone.
9.	Pair your phone with Bluetooth Module and open Bluetooth app then give commands As per the Code.





Program:
char data; //Variable for storing received data void setup()
{
Serial.begin(9600); //Sets the baud for serial data transmission 
pinMode(13, OUTPUT); //Sets digital pin 13 as output pin 
pinMode(12, OUTPUT); //Sets digital pin 12 as output pin
}
void loop()
{
if(Serial.available() &gt; 0) // Send data only when you receive data:
{
data = Serial.read(); //Read the incoming data and store it into variable data
Serial.print(data); //Print Value inside data in Serial monitor Serial.print(&quot;\n&quot;);
if(data == &#39;0&#39;)
{ // Checks whether value of data is equal to 0 
digitalWrite(13, HIGH); //If value is 0 then LED at 13th pin turns ON
digitalWrite(12,LOW); // and 12th pin turns off
}
else if(data == &#39;1&#39;)
{ // Checks whether value of data is equal to 1
digitalWrite(12, HIGH); //If value is 1 then LED at 12th pin turns ON
digitalWrite(13, LOW); //and LED at 13th pin turns OFF
}
else
{
digitalWrite(13, LOW); //if any other value both LED turns off 
digitalWrite(12,LOW);
}
}
}
Precautions:
•	Take care about given power supply (12V).
•	Jumper wires given carefully whenever given circuit connection.
RESULT: Two Actuators are controlled by smart phone using Bluetooth module.

# IOT
