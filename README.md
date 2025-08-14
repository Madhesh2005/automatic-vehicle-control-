AUTOMATIC VEHICAL CONTROL
The Automatic Vehicle Control System is designed to detect obstacles on the road and automatically control the vehicle’s motion without driver intervention. The system uses sensors, a microcontroller, and motor control circuits to enhance road safety, reduce human error, and improve driving comfort.  


PROJECT TITLE

Automatic Vehicle Control using Arduino in Tinkercad

PROJECT IDEA

We’ll create a small robotic vehicle in Tinkercad that can automatically detect obstacles using an ultrasonic sensor and control its movement using a motor driver and DC motors. This is a scaled-down simulation of real-world automatic braking and collision avoidance systems in modern cars.

COMPONENTS IN TINKERCAD

Arduino Uno – main controller (ECU)

HC-SR04 Ultrasonic Sensor – detects obstacles

L293D Motor Driver IC – controls motors

2x DC Motors + Wheels – movement of vehicle

Breadboard – connections

Jumper Wires – wiring

Power Source – Arduino USB or battery pack (in simulation)

Working Principle

Sensor detection: Ultrasonic sensor measures distance to the object ahead.

Decision-making: Arduino processes the reading and compares it with the safe distance.

Action:

If distance > safe limit → motors move forward.

If distance ≤ safe limit → motors stop or reverse. 

PROJECT CIRCUIT DIAGRAM:


<img width="1366" height="544" alt="Amazing Esboo-Migelo" src="https://github.com/user-attachments/assets/34fb6d00-ac0a-4130-9580-43356b6537b4" />


PROJECT BLOCK DIAGRAM:


<img width="646" height="444" alt="image" src="https://github.com/user-attachments/assets/0f77f67b-a0e6-44ec-be5d-70ba3f0d06a6" />



ARDUNIO CODE
#define trigPin 9
#define echoPin 10
#define motor1pin1 2
#define motor1pin2 3
#define motor2pin1 4
#define motor2pin2 5

long duration;
int distance;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(motor1pin1, OUTPUT);
  pinMode(motor1pin2, OUTPUT);
  pinMode(motor2pin1, OUTPUT);
  pinMode(motor2pin2, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  // Trigger the ultrasonic sensor
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  // Read the echo
  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");
  Serial.println(distance);

  if (distance > 15) { // safe distance in cm
    // Move forward
    digitalWrite(motor1pin1, HIGH);
    digitalWrite(motor1pin2, LOW);
    digitalWrite(motor2pin1, HIGH);
    digitalWrite(motor2pin2, LOW);
  } else {
    // Stop
    digitalWrite(motor1pin1, LOW);
    digitalWrite(motor1pin2, LOW);
    digitalWrite(motor2pin1, LOW);
    digitalWrite(motor2pin2, LOW);
  }

  delay(100);
}




ALGORTHM

Steps in Tinkercad

Open Tinkercad Circuits.

Create a New Circuit.

Add Arduino Uno, HC-SR04 sensor, L293D motor driver, DC motors, breadboard.

Connect components according to the pin mapping in the code.

Paste the Arduino code.

Start simulation and move the obstacle slider in the ultrasonic sensor to test automatic stopping.

Do you want me to prepare that diagram for you? 



SIMULATION: 
https://www.tinkercad.com/things/jlWrPaS5AUW-amazing-esboo-migelo/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=X9UK3byCoFg9GS_62RYDzxYTs-ZMoY_x40Vv94UxD9Y

