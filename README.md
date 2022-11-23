# EXPERIMENT NO 05 INTERFACING ANALOG OUTPUT SERVO MOTOR WITH ARDUINO

## AIM:
To interface an Analog output (servo motor) and modify the angular displacement of the servo using PWM signal .
COMPONENTS REQUIRED:
1.	Servo motor of choice (9v is preferred )
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 
6.	Servo rated power supply (dc source )


## THEORY:
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

### CIRCUIT DIAGRAM:
 
 
 ![image](https://user-images.githubusercontent.com/36288975/163544618-6eb8a7b5-7f1a-428a-8d9f-fd899b145efb.png)

#### FIGURE 04 CIRCUIT DIAGRAM

## PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select your board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device.


## PROGRAM :
```
#include<Servo.h>

Servo myservo;
int value;
double angle;
void setup()
{
  Serial.begin(9600);
  myservo.attach(9);
}
void loop()
{
  value = analogRead(A0);
  angle = map(value, 0, 1023,0,180);
  Serial.println(angle);
  myservo.write(angle);
}
```
## Output:
### Before Simulation:
![00](https://user-images.githubusercontent.com/94164665/203466338-e94189b9-a58b-4b3c-8bb4-6c9d213bbf6c.jpg)

### After Simulation:
![01](https://user-images.githubusercontent.com/94164665/203466347-33c435e5-b525-4798-a477-dd91760da5d0.jpg)
![02](https://user-images.githubusercontent.com/94164665/203466357-c8343c31-9b0d-4a97-8858-9dc2004eaa4c.jpg)

### Serial Monitor and Graph:

![03](https://user-images.githubusercontent.com/94164665/203466364-f21e2f5b-87a9-4fdb-8149-a7802cf2af98.jpg)


## RESULTS: 
Arduino uno interfacing with servo motor is learned and angular position is controlled using PWM signal.
