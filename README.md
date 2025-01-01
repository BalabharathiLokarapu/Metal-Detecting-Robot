# Metal-Detecting-Robot
# Updated README for Metal-Detecting-Robot
This is a new update to the README file.


The Metal Detecting Robot is an innovative project designed to identify metal objects using a proximity sensor. The robot utilizes an Arduino Uno for control and a motor driver for movement. When a metal object is detected, the robot halts its movement, ensuring safety and precision.

## Features
- **Metal Detection**: Detects metallic objects using a proximity sensor.
- **Automation**: Stops movement automatically upon detection.
- **Easy to Build**: Requires minimal components and straightforward assembly.
- **Applications**: Useful for landmine detection, industrial safety, and educational demonstrations.

## Components Used
1. Arduino Uno
2. Proximity Sensor
3. Motor Driver (e.g., L298N)
4. DC Motors
5. Chassis for the Robot
6. Power Supply (Battery)
7. Connecting Wires

## How It Works
1. The proximity sensor continuously scans the area for metallic objects.
2. When metal is detected, a signal is sent to the Arduino Uno.
3. The Arduino Uno processes the signal and stops the motor driver, halting the robot's movement.

## Applications
- **Landmine Detection**: A safer approach to detecting and marking potential threats.
- **Industrial Safety**: Identifies metallic debris to prevent damage to machinery.
- **Education**: A hands-on project to learn about sensors, robotics, and automation.

## Arduino Code
```cpp
// Example code for Metal Detecting Robot
#include <Servo.h>

#define METAL_SENSOR_PIN A0
#define MOTOR_DRIVER_EN 9

void setup() {
    pinMode(METAL_SENSOR_PIN, INPUT);
    pinMode(MOTOR_DRIVER_EN, OUTPUT);
    Serial.begin(9600);
}

void loop() {
    int sensorValue = analogRead(METAL_SENSOR_PIN);
    if (sensorValue > 500) { // Threshold for metal detection
        digitalWrite(MOTOR_DRIVER_EN, LOW); // Stop motors
        Serial.println("Metal detected! Robot stopped.");
    } else {
        digitalWrite(MOTOR_DRIVER_EN, HIGH); // Keep motors running
        Serial.println("No metal detected. Robot moving.");
    }
    delay(200);
}
