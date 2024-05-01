# Ultrasonic Distance Measurement Simulation in Tinkercad

## Overview

The Ultrasonic Distance Measurement Simulation in Tinkercad is a virtual representation of a system that measures distances using an ultrasonic sensor. This project utilizes Tinkercad, a browser-based simulation platform, to create and test the circuit virtually. The system consists of an Arduino Uno microcontroller, an ultrasonic distance sensor (HC-SR04), and two LEDs (red and green). The LEDs provide visual feedback based on the distance measured by the ultrasonic sensor.


## Components Used

<img src="https://github.com/AmruthaRajsheker/Simulation-on-Distance-measurement-in-Tinkercad/assets/119475943/6f8e932f-f520-4488-9233-e5a017209e6a" alt="description" style="width: 70%; height: auto;">


1. **Arduino Uno R3**: The Arduino Uno is a microcontroller board based on the ATmega328P. It acts as the brain of the system, processing sensor data and controlling the LEDs based on distance measurements.

2. **Ultrasonic Distance Sensor (4-pin)**: The ultrasonic distance sensor, often referred to as HC-SR04, is used to measure distances by emitting ultrasonic waves and calculating the time it takes for the waves to bounce back. It consists of two cylindrical modules - a transmitter and a receiver.

3. **Red LED**: The red LED serves as an indicator for objects detected within a certain range (e.g., within 10 cm). It blinks to signal proximity.

4. **Green LED**: The green LED serves as an indicator for objects detected beyond the specified range. It blinks to signal that the detected object is at a safe distance.

5. **1 kΩ Resistor (R1, R2)**: These resistors are used to limit the current flowing through the LEDs, preventing them from burning out due to excessive current flow. They are connected in series with the LEDs to control the brightness and protect them from damage.

</br>

## Circuit Diagram

#### Schemantic view

![AMRUTHA - MINI PROJ IIOT_page-0002](https://github.com/AmruthaRajsheker/Simulation-on-Distance-measurement-in-Tinkercad/assets/119475943/ee2ef13d-5090-491b-bd19-7ce722a8d5cf)

#### Circuit view

![image](https://github.com/AmruthaRajsheker/Simulation-on-Distance-measurement-in-Tinkercad/assets/119475943/571c12de-8d3a-4746-a07a-69cc40108c46)


## Procedure: Building the Circuit in Tinkercad

#### Step 1: Open Tinkercad

1. Go to the Tinkercad website (www.tinkercad.com) and log in to your account. If you don't have an account, you can sign up for free.

2. Once logged in, create a new project by clicking on the "Create new design" button.

#### Step 2: Add Components to the Workspace

1. Click on the "Components" panel on the right side of the screen to open it.

2. Search for and drag the following components to the workspace:
   - Arduino Uno
   - Ultrasonic Distance Sensor (HC-SR04)
   - Red LED
   - Green LED
   - Resistors (1 kΩ)

#### Step 3: Connect Components

1. Arrange the components on the workspace to resemble the circuit diagram. Place the Arduino Uno at the center, and position the ultrasonic sensor, LEDs, and resistors accordingly.

2. Connect the components as follows:
   - Connect the VCC (5V) pin of the Arduino Uno to the VCC pins of the ultrasonic sensor, LEDs, and resistors.
   - Connect the GND (ground) pin of the Arduino Uno to the GND pins of the ultrasonic sensor, LEDs, and resistors.
   - Connect the digital pin 3 (D3) of the Arduino Uno to the anode (positive) pin of the red LED through a resistor (R1).
   - Connect the digital pin 4 (D4) of the Arduino Uno to the anode (positive) pin of the green LED through a resistor (R2).
   - Connect the trig pin of the ultrasonic sensor to digital pin 7 (D7) of the Arduino Uno.
   - Connect the echo pin of the ultrasonic sensor to digital pin 6 (D6) of the Arduino Uno.

#### Step 4: Verify Connections

1. Double-check all connections to ensure they match the circuit diagram and there are no loose connections.

#### Step 5: Test the Circuit

1. Click on the "Code" panel on the right side of the screen to open it.

2. Write the Arduino code for distance measurement and LED control according to your requirements.

3. Click on the "Start Simulation" button to test the circuit and observe the behavior of the LEDs based on distance measurements.

#### Step 6: Fine-Tuning and Experimentation

1. Experiment with different distances and observe how the LEDs respond.

2. Fine-tune the code and circuit as necessary to achieve the desired behavior.


#### Step 7: Save and Share

1. Once satisfied with the circuit, save your project by clicking on the "Save" button.

2. You can also share your project with others by clicking on the "Share" button and copying the link.

#### Start the Working

Now that you've built the circuit in Tinkercad, you can start testing its functionality. Run the simulation to see how the LEDs respond to different distances measured by the ultrasonic sensor. Adjust the code and experiment with various configurations to achieve the desired behavior of the system. Have fun tinkering!




## Code

```cpp
const int trigpin =7 ;
const int echopin =6;
long duration ;
float distance ;
int red = 9 ;
int green = 8 ;

void setup() {
  pinMode (red,OUTPUT);
  pinMode (green,OUTPUT);
  pinMode (trigpin,OUTPUT);
  pinMode (echopin,INPUT);
  Serial.begin(9600);
}
```
```cpp
void loop() {
  digitalWrite(trigpin , LOW );
  delay (100);
  digitalWrite(trigpin , HIGH);
  delay (100);
  digitalWrite(trigpin , LOW );
  duration = pulseIn(echopin , HIGH);
  distance = duration*0.034/2;
  Serial.print ("Distance = ");
  Serial.print (distance);
  Serial.println ("CMS  ");
  if (distance < 10)
  {
    digitalWrite(red,LOW);
    delay(100);
    digitalWrite(red,HIGH);
    delay(100);
    
  }
  else
  {
    digitalWrite(green,LOW);
    delay(100);
    digitalWrite(green,HIGH);
    delay(100); 
  }
}
```

## OUTPUT 
<img src="https://github.com/AmruthaRajsheker/Simulation-on-Distance-measurement-in-Tinkercad/assets/119475943/cff45135-8ee8-4838-9d0f-83daafb7320f" alt="description" style="width: 40%; height: auto;">


