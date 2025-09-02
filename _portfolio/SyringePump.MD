---
title: "Syringe Pump"
excerpt: "This syringe pump can deliver precise, programmable flow of fluids contained in a syringe, with support for multiple syringe sizes!"
header:
  image: /assets/img/banner SP.JPG
  teaser: /assets/img/banner SP.JPG
gallery:
  - image_path: assets/img/SyringePump_Project.JPG
  - image_path: assets/img/Assembling SP.JPG
  - image_path: assets/img/Dimensional Drawing SP.JPG
  - image_path: assets/img/Wiring SP.JPG
  - image_path: assets/img/CAD model SP.JPG
  - image_path: assets/img/Enclosure SP.JPG

---

I worked on a team to design and build a custom syringe pump capable of delivering precise flow rates between 0.1 mL/min and 5 mL/min with compatibility across two syringe sizes. This makes it well-suited for applications in microfluidics, biomedial reasearch, or controlled drug delivery. 

Commercial syringe pumps can cost several hundred dollars, so instead of buying one, our team engineeringed a DIY version. We combined CAD modeling, 3D printing, electrical wiring and Arduino programming to create a reliable device powered by a stepper motor and lead screw. The system integrates flow rate control, limit switches, and LED indicators. These features make it safe, accurate, and user-friendly. 

# Features

* **Precise Flow Control.** The syringe pump is driven by a NEMA 17 stepper motor coupled to a lead screw, allowing highly accurate and repeatable control of fluid flow. Flow rates ranging from 0.1 mL/min to 5 mL/min can be set directly in the Arduino program, ensuring flexibility across a wide range of applications.
* **Interchangeable Syringe Compatibility.** Designed to accommodate syringes from 10 mL to 20 mL, the pump features tool-free adjustment for quick changes. The syringe is supported on both ends to prevent sagging during operation, maintaining accuracy even with viscous fluids.
* **User-Friendly Controls & Indicators.** Operation is managed through a single latching start/pause button, with a limit switch to automatically stop the motor when the syringe is empty. A tri-color LED provides real-time status feedback: green when running, yellow when paused, and red when out of liquid.
* **Safe and Organized Electronics.** All electrical components, including the Arduino, motor driver, and power supply, are enclosed in a custom 3D-printed housing. Wiring is carefully routed with heat-shrink protection for durability and safety, preventing short circuits or accidental contact with liquids.

# CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a4cf95ba431c8819cd?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

# Arduino Code
//Syringe Pump Arduino Code 
```cpp
#include <AccelStepper.h>

// Establishes what pins control what functionality
#define DIR_PIN 2
#define STEP_PIN 3
#define BUTTON_PIN 4
#define LIMIT_SWITCH_PIN 5
#define LED_RED 8
#define LED_GREEN 9
#define LED_BLUE 10

float setFlowRate = 20; // Flow rate in mL/min 
float setDiameter = 19.2; // Syringe diameter in mm
bool pumpRunning = false; // Pump is off by default
float stepsPerRevolution = 800; // Steps per Revolution
float leadScrewPitch = 2.0; // Lead Screw Pitch of mm per revolution

AccelStepper stepperX(AccelStepper::DRIVER,STEP_PIN,DIR_PIN); // Interfaces with motor driver

void setup() {
  // Sets the following pins as read pins
  pinMode(BUTTON_PIN, INPUT_PULLUP);
  pinMode(LIMIT_SWITCH_PIN, INPUT_PULLUP);
  // Sets the following pins as write pins
  pinMode(LED_RED, OUTPUT);
  pinMode(LED_GREEN, OUTPUT);
  pinMode(LED_BLUE, OUTPUT);

  stepperX.setMaxSpeed(1000);
  stepperX.setSpeed(convertFlowRate(setFlowRate,setDiameter)); //Converts from flow rate to step speed
}

void loop() {
    pumpRunning = digitalRead(BUTTON_PIN)==LOW; //Records in ON/OFF is pressed
    if (digitalRead(LIMIT_SWITCH_PIN)==HIGH){// Checks if limit switch is pressed
      pumpRunning = false;// Records pump not running
      updateLEDs();
    } else if (pumpRunning){// Checks if pump is running
      stepperX.runSpeed();// Motor rotates
      updateLEDs();
    } else{
      updateLEDs();
    }
}

float calculateStepsPerSecond(float flowRate, float syringeDiameter) { 
// Convert flow rate (mL/min) to steps per second 
float linearSpeed = flowRate / (PI * (syringeDiameter / 2.0) * 
(syringeDiameter / 2.0) * 1000.0); // mm/s 
float stepsPerSecond = linearSpeed * stepsPerRevolution / leadScrewPitch; 
return stepsPerSecond; 
}

// Updates the color of the LED
void updateLEDs() {
  if (pumpRunning) {
    digitalWrite(LED_GREEN, HIGH); // Updates LED to green
    digitalWrite(LED_BLUE, LOW);
    digitalWrite(LED_RED, LOW);
  }else if (digitalRead(LIMIT_SWITCH_PIN)==HIGH) {// If syringe is empty
    digitalWrite(LED_GREEN, LOW);
    digitalWrite(LED_BLUE, LOW);
    digitalWrite(LED_RED, HIGH); // Updates LED to red
  } else {
    digitalWrite(LED_GREEN, HIGH); // Updates LED to yellow
    digitalWrite(LED_BLUE, LOW);
    digitalWrite(LED_RED, HIGH);
  }
}


{% include gallery caption="Syringe Pump Project Gallery" %}
