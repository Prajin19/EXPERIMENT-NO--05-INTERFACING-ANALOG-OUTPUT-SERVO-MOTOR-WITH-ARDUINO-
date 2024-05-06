# EXPERIMENT NO 05 INTERFACING ANALOG OUTPUT SERVO MOTOR WITH ARDUINO
###  NAME: Prajin S
###  DATE: 01-05-2024
###  ROLL NO : 212223230151
###  DEPARTMENT: Artificial Intelligence and Data Sceince




### AIM
To interface an Analog output (servo motor) and modify the angular displacement of the servo using PWM signal .
COMPONENTS REQUIRED:
1.	Servo motor of choice (9v is preferred )
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 
6.	Servo rated power supply (dc source )


### THEORY
Servo motors and are constructed out of basic DC motors, by adding:
•	 gear reduction
•	 a position sensor for the motor shaft
•	 an electronic circuit that controls the motor's operation
Typically, a potentiometer (variable resistor) measures the position of the output shaft at all times so the controller can accurately place and maintain its setting.
Servo motors are used for angular positioning, such as in radio control airplanes.  They typically have a movement range of 180 deg but can go up to 210 deg.The output shaft of a servo does not rotate freely, but rather is made to seek a particular angular position under electronic control. 


![image](https://user-images.githubusercontent.com/36288975/163544439-1f477927-fcd4-42f0-9ce4-c863fdbf1210.png)



#### Figure-01 SERVO MOTOR SPLIT VIEW 
Control 
An external controller (such as the Arduino) tells the servo where to go with a signal know as pulse proportional modulation (PPM) or pulse code modulation (which is often confused with pulse width modulation, PWM). PWM uses 1 to 2ms out of a 20ms time period to encode its information.
 
 
 ![image](https://user-images.githubusercontent.com/36288975/163544482-3027136f-7135-4f3d-a23f-8dc2fe04194d.png)

#### Figure-02 SERVO MOTOR PINS

 ![image](https://user-images.githubusercontent.com/36288975/163544513-ca497421-e6ba-4f91-871f-5cfba77f22a8.png)


#### Figure-03 SERVO MOTOR OVERVIEW 

 


 





## CIRCUIT DIAGRAM
 
 
 ![image](https://user-images.githubusercontent.com/36288975/163544618-6eb8a7b5-7f1a-428a-8d9f-fd899b145efb.png)

#### FIGURE 04 CIRCUIT DIAGRAM

### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select your board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device.


### PROGRAM :
```
#include<Servo.h>
Servo sa;
int po=0,red=9,gre=8;
void setup()
{
  sa.attach(6);
  Serial.begin(9600);
  pinMode(red,OUTPUT);
  pinMode(gre,OUTPUT);
}
void loop()
{
  for(po=0;po<=180;po+=5)
  {
    sa.write(po);
    delay(200);
  	Serial.println(po);
    if(po>=120)
    {
    	digitalWrite(red,HIGH);
    	delay(200);
    	digitalWrite(red,LOW);
    	delay(200);
  	}
  }
  for(po=180;po>=0;po-=5)
  {
    sa.write(po);
  	delay(200);
  	Serial.println(po);
    if(po<=120)
  	{
    	digitalWrite(gre,HIGH);
    	delay(200);
    	digitalWrite(gre,LOW);
    	delay(200);
  	}  
  } 
}
```
![Screenshot 2024-03-22 161158](https://github.com/Prajin19/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/144979377/da2e687a-9acf-447d-a1ff-d51a1d3e5233)
#### FIGURE 05 GRAPH

### Simulation Output
![Screenshot 2024-03-22 161333](https://github.com/Prajin19/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/144979377/e6b7fb01-6bfd-4db7-9ff3-30f723daa490)
#### FIGURE 06 OFF CONDITION

![Screenshot 2024-03-22 161219](https://github.com/Prajin19/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/144979377/cb385c4e-fc6d-4032-a84e-c043278e0bf3)
#### FIGURE 07 ON CONDITION(POS<120,GREEN)

![Screenshot 2024-03-22 161301](https://github.com/Prajin19/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/144979377/f24fcf53-4edf-4bb8-ae39-31134f86a794)
#### FIGURE 08 ON CONDITION (POS>120,RED)

![Screenshot 2024-03-22 161432](https://github.com/Prajin19/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/144979377/4ffc2880-7245-484c-910c-ec26d555aab9)
#### FIGURE 09 SCHEMATIC SIMULATION





### RESULTS: 
Arduino uno interfacing with servo motor is learned and angular position is controlled using PWM signal.
