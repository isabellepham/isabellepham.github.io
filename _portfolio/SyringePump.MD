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
<iframe src="https://myhub.autodesk360.com/ue2df0af5/shares/public/SH35dfcQT936092f0e437224cd558fdcdc2f?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>


{% include gallery caption="Syringe Pump Project Gallery" %}
