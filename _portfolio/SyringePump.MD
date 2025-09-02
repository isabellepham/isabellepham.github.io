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

* **Precise Flow Control:** The syringe pump is driven by a NEMA 17 stepper motor coupled to a lead screw, allowing highly accurate and repeatable control of fluid flow. Flow rates ranging from 0.1 mL/min to 5 mL/min can be set directly in the Arduino program, ensuring flexibility across a wide range of applications.
* **Interchangeable Syringe Compatibility:** Designed to accommodate syringes from 10 mL to 20 mL, the pump features tool-free adjustment for quick changes. The syringe is supported on both ends to prevent sagging during operation, maintaining accuracy even with viscous fluids.
* **User-Friendly Controls & Indicators:** Operation is managed through a single latching start/pause button, with a limit switch to automatically stop the motor when the syringe is empty. A tri-color LED provides real-time status feedback: green when running, yellow when paused, and red when out of liquid.
* **Safe and Organized Electronics:** All electrical components, including the Arduino, motor driver, and power supply, are enclosed in a custom 3D-printed housing. Wiring is carefully routed with heat-shrink protection for durability and safety, preventing short circuits or accidental contact with liquids.



# Off-The-Shelf Parts

| Component                                                                 | Quantity |
|---------------------------------------------------------------------------|----------|
| [250 mm Lead Screw (2 mm pitch, 2 mm lead)](https://www.amazon.com/dp/B07R1H5ZMV/ref=cm_sw_em_r_mt_dp_0YZ13D4HQBGW2Z86PBV1?_encoding=UTF8&psc=1) | 1 |
| [250 mm Lead Screw (2 mm pitch, 8 mm lead)](https://amzn.to/3infwI0) | 1 |
| [1/4" x 8 mm Flexible Coupling](https://openbuildspartstore.com/1-4-x-8mm-flexible-coupling/) | 1 |
| [200 mm Linear Rod (8 mm diameter)](https://www.amazon.com/dp/B07MPGWJMS/ref=cm_sw_em_r_mt_dp_X5AQS0ES7JH8JG83AAZ3) | 2 |
| [LM8UU Linear Bearing (8 mm diameter rod)](https://www.amazon.com/dp/B07R1H5ZMV/ref=cm_sw_em_r_mt_dp_0YZ13D4HQBGW2Z86PBV1?_encoding=UTF8&psc=1) | 2 |
| [2040 Aluminum Extrusion (1 ft length)](https://openbuildspartstore.com/v-slot-20x40-linear-rail/) | 1 |
| [Nema 17 Stepper Motor](https://www.amazon.com/gp/product/B07LF898KN/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1) | 1 |
| [MEAN WELL RQ-65D AC-DC Power Supply (Quad Output 5V/12V/24V/12V 4A)](https://grabcad.com/library/mean-well-rt-65-1) | 1 |
| [Arduino Uno](https://www.amazon.com/dp/B005T9HGLI/ref=cm_sw_em_r_mt_dp_A8CZ056TM52EJGZTGZGR?_encoding=UTF8&psc=1) | 1 |
| [A4988 Stepper Driver](https://www.amazon.com/dp/B007R9TUJE/ref=cm_sw_em_r_mt_dp_TY8JGK0CJD1JEJM4BNNJ) | 1 |
| [Small Breadboard](https://www.amazon.com/dp/B01FFGAKK8/ref=cm_sw_em_r_mt_dp_V0YKTYKDWMR8WHTKA53T?_encoding=UTF8&psc=1) | 1 |
| [Panel Mount Latching Push Button (On/Off)](https://www.amazon.com/dp/B082VYXDF1/ref=cm_sw_em_r_mt_dp_N6Q28CAGPAYCKCSJKDDC?_encoding=UTF8&psc=1) | 1 |
| [Panel Mount Momentary Push Button (Bonus only)](https://amzn.to/3VxQ29h) | 1 |
| [Limit Switch](https://www.amazon.com/gp/product/B07X142VGC) | 1 |
| [RGB Common Cathode LED](https://www.amazon.com/dp/B0194Y6MW2/ref=cm_sw_em_r_mt_dp_FW3CFQT7ZGFQ2R04N6G3?_encoding=UTF8&psc=1) | Supplied in Lab |
| Wires, fasteners, resistors, misc. lab supplies | Supplied in Lab |



# 3D Printed Parts

| 3D Printed Part        | Purpose / Function |
|-------------------------|--------------------|
| Stepper Motor Mount     | Secures the Nema 17 stepper motor to the aluminum extrusion |
| Carriage / Plunger Holder | Connects the syringe plunger to the lead screw nut and moves along the rails |
| Linear Bearing Holders  | Press-fit mounts for LM8UU linear bearings to support the moving carriage |
| Syringe Clamp / Holder  | Holds syringes of 10–20 mL securely in place without tools |
| Electronics Enclosure   | Protects Arduino, power supply, stepper driver, and wiring from users/liquids |
| Limit Switch Mount      | Holds the endstop switch in position to detect plunger travel limits |
| Structural Brackets     | Additional brackets/adapters needed for mounting and stability |



# CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a4cf95ba431c8819cd?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>



# Arduino Code
[View Arduino Code Here](https://github.com/isabellepham/isabellepham.github.io/blob/c34c52e08708b741211094d6f41af621a22731a7/code/syringe%20pump%20arduino) 



# How to Operate the Syringe Pump 
1. **Prepare the Syringe**  
   - Fill a syringe (10–20 mL) with the desired liquid.  
   - Secure the syringe into the printed holder so it is supported at both ends.  
   - Insert the plunger into the carriage holder.  

2. **Power On**  
   - Connect the power supply to mains and ensure the Arduino is powered.  
   - The RGB LED should light up, indicating the system status (Green = running, Yellow = paused, Red = empty).  

3. **Set Flow Rate**  
   - Open the Arduino IDE Serial Monitor (or adjust code variables if predefined).  
   - Enter or confirm the desired flow rate (mL/min).  

4. **Start the Pump**  
   - Press the latching push button to begin pumping.  
   - The carriage will move along the lead screw, pushing the syringe plunger.  

5. **Pause / Resume**  
   - Press the latching button again to pause pumping.  
   - Press once more to resume.  

6. **Limit Switch Safety**  
   - The pump will automatically stop when the plunger reaches its end position.  

7. **Shut Down**  
   - After use, press the button to stop operation.  
   - Turn off and unplug the power supply before removing the syringe.  



{% include gallery caption="Syringe Pump Project Gallery" %}
