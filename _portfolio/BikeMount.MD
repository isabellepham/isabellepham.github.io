---
title: "Bike Phone Mount"
excerpt: "A top-down–modeled, multi-material bike phone mount featuring a print-in-place detent rotation mechanism and a flexible TPU phone case for secure, vibration-resistant riding."
header:
  image: /assets/img/5 BikeMount_Banner.jpg
  teaser: /assets/img/5 BikeMount_Banner.jpg
gallery:
  - image_path: assets/img/5 BikeMount-1.JPG
  - image_path: assets/img/5 BikeMount-2.JPG
  - image_path: assets/img/5 BikeMount-3.JPG
  - image_path: assets/img/5 BikeMount-4.JPG
  - image_path: assets/img/5 BikeMount-5.JPG
  - image_path: assets/img/5 BikeMount-6.JPG
  - image_path: assets/img/5 BikeMount-7.JPG
  - image_path: assets/img/5 BikeMount-8.JPG
  - image_path: assets/img/5 BikeMount-CrossSection.png
  
---

I designed and fabricated a functional rotating bike phone holder using Fusion 360 and a top-down modeling approach. Beginning with the phone case as the primary reference geometry, I built the clamp, rotating hub, and detent components directly around it to ensure precise alignment and smooth motion. The assembly incorporates a spring-loaded detent mechanism that enables the phone to snap cleanly between portrait and landscape orientations, along with a TPU phone case that provides a tight, cushioning grip during riding.

---
# Top-Down Modeling
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
A description of top-down modeling and how it was leveraged in this assignment
</p>

Top-down modeling is a design approach where the overall layout and reference geometry are established first, and individual components are then created in context around that shared framework. Instead of designing parts independently, everything is built from common sketches, reference planes, and parameters, which ensures that components align correctly and update predictably when changes are made.

In this assignment, top-down modeling was used by treating the phone case as the central reference geometry. All major components—such as the rotating interface, detent mechanism, and mounting features—were created directly around the phone case’s dimensions and position. By building each component in place, the holder’s grip features, clearances, and rotation geometry could be tuned precisely to the phone without needing a separate assembly step to test alignment.

This approach also made it easier to design the rotation and detent mechanism because the interacting parts (recesses, bearing seats, spring pockets, and the rotating hub) could be sketched and adjusted while visible together. Parametric dimensions were used to control clearances and 3D-printing tolerances, allowing quick adjustments to the rotation feel and snapping force.

Finally, because each component was modeled in its final assembled location and later joined using as-built joints, the entire design remained consistent and easy to modify. Any change to the phone case or key parameters automatically propagated through the linked features, which is the core advantage of the top-down modeling approach.


# Rationale
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
What type of rotation mechanism did you use? Does it work well?
Did you have to change any dimensions to account for the 3d printing process? 
What type of 3d printing did you use? Why?
</p>

The bike phone mount was created using a top-down modeling workflow in Fusion 360. Separating the system into distinct functional components made it easier to iterate, adjust tolerances, and troubleshoot mechanical failures. The mount consists of four primary parts:

1. Phone Case – TPU case that interfaces with the phone and connects to the detent mechanism.
2. Rotating Hub – Circular PLA component containing the detent pockets and a heat-set insert.
3. Mount Body – PLA structure that houses the detent mechanism and connects to the handlebar cuff.
4. Handlebar Cuff – ABS component that tightens around the bike handlebar.

## Detent Mechanism Overview

For the rotation interface, I used a simple spring-loaded detent mechanism because it was straightforward to design, print, and integrate with off-the-shelf hardware. The mechanism consists of:
- a compression spring,
- a ball bearing, and
- angled recesses in the rotating hub.

As the phone turns, the ball compresses into the spring and snaps into each recess, creating clear, discrete rotational positions for portrait and landscape use. The mechanism worked reliably in practice and provided a satisfying “click” during rotation. The strength of the compression spring had a noticeable effect on functionality—stronger springs increased locking force and stability, while weaker springs made rotation easier but reduced tactile feedback.

## Initial CAD Development

### Phone Case

The phone case was adapted from a previous parametric design for an iPhone 15. Adjustable parameters—case thickness, width, height, and button/camera cutouts—made it easy to repurpose for this mount.

To integrate the rotational hardware, the back panel thickness was increased by 4.25 mm, resulting in a final thickness of 6.824 mm to fit an M5 screw connecting the phone to the rotating hub.

To ensure smooth assembly after printing, I also incorporated small dimensional offsets around the contact surfaces. TPU often expands slightly during printing, so these offsets prevented overly tight fits and ensured the case would seat against the hub without post-processing.

<p align="center">
  <img src="/assets/img/5 BikeMount-Figure 1.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 1. First Iteration of CAD Phone Case for iPhone 15</em>
</p>

### Rotating Hub

The rotating hub was modeled as a 30 mm diameter disc with five 8.1 mm detent pockets arrayed around the perimeter. These pockets were offset slightly from the center plane instead of being cut directly in half—this prevented the ball from getting trapped and ensured smooth transitions between detents.

A recess was added for a heat-set insert, allowing the M5 screw from the phone case to anchor firmly into the hub.

Because the detent mechanism is sensitive to friction and tolerance stacking, I made fine adjustments to the pocket diameter and recess depth so the ball could travel freely without binding. These minor changes made the mechanism more reliable and improved the clarity of each “click.”

<p align="center">
  <img src="/assets/img/5 BikeMount-Figure 2.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 1. First Iteration of CAD Rotating Hub for Detent Mechanism</em>
</p>

### Mount Body

The mount body serves three roles:
1. enclosing the detent mechanism
2. holding the spring and ball securely in alignment
3. connecting the rotating hub to the handlebar cuff

The enclosure began as a rectangular housing sized to provide ~1 mm radial clearance around the hub. A pocket was added for the spring and ball.
To ensure the phone would not collide with the enclosure when rotated into landscape mode, a construction circle equal to the phone’s diagonal was used in Fusion 360 to test possible rotations.

Originally, the housing left the hub uncovered on one side, but I later added internal panels to fully enclose the mechanism. Only the screw opening remained exposed so the mechanism could be assembled.

The base of the mount body included two countersunk M5 holes for attachment to the handlebar cuff.

<p align="center">
  <img src="/assets/img/5 BikeMount-Figure 3.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 1. First Iteration of CAD Mount Body</em>
</p>

### Handlebar Cuff

The handlebar cuff was designed to clamp around a 22.5 mm diameter handlebar. It was extruded to 11 mm to accommodate heat-set inserts and M5 hardware.

Two extended clamping arms held an M5 screw + nut, providing adjustable clamping force so the mount could be tightened securely without slipping during bike movement.

<p align="center">
  <img src="/assets/img/5 BikeMount-Figure 4.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 1. First Iteration of CAD Handlebar Cuff</em>
</p>

## **Printing Approach and Material Selection**

All components were fabricated using FFF (fused filament fabrication). This method allowed rapid iteration, fast turnaround between design changes, and reliable dimensional accuracy—especially important for the mechanical interfaces, heat-set inserts, and detent mechanism.

Material choices were based on mechanical requirements:
1. TPU – Used for the phone case to provide flexibility, shock absorption, and a non-scratching grip.
2. PLA – Used for the mount body and rotating hub for rigidity, crisp detent geometry, and reliable tolerances.
3. ABS – Used for the handlebar cuff for toughness and higher heat resistance during outdoor use.

Heat-set inserts bonded cleanly into the thermoplastics, producing strong and repeatable threaded connections.

## Initial Printing and Assembly

The first iteration assembled without major dimensional issues: 
- The ABS handlebar cuff clamped securely using 20 mm M5 screws.
- The mount body attached using heat-set inserts and 12 mm M5 screws.
- The rotating hub fit smoothly inside the enclosure with the intended functional clearance.

The TPU phone case attached to the hub with a single M5 screw.

Testing the detent mechanism by rotating the hub manually worked perfectly—each recess produced a distinct click, and the ball and spring moved freely.

However, once the phone case was attached, a critical problem appeared.

With the phone installed, the case could rotate freely around the central screw without engaging the hub.
Because TPU is soft, a single screw could not transmit enough torque to the rigid PLA hub. The phone rotated—but the detent mechanism did not.

## Attempted Fix #1: Through-Bolt Reinforcement

I attempted a quick fix by melting a channel through the hub and inserting a 20 mm M5 through-bolt secured with a nut. This increased clamping force, but did not solve the underlying problem. With only one point of connection, the TPU still twisted independently of the hub.

## **Second Iteration: Three-Screw Torque Transfer System**

To achieve reliable torque transfer, I redesigned the interface to use three M5 screws instead of one. A single screw allows rotation around its axis. Three screws form a triangular constraint, which prevents shear deformation in the TPU, eliminates rotational slippage, and distributes torque evenly into the rigid PLA hub.

This redesign created a mechanically locked interface between the phone case and rotating hub.

## Additional CAD Adjustments

To avoid reprinting the mount body and cuff, only the hub and enclosure geometry were modified. The enclosure was flipped so the solid panel faced the phone case. A 20 mm M5 through-screw passed through the phone, hub, and enclosure. Two additional screws used heat-set inserts for symmetrical loading.

## Reprints and Final Assembly

Reprinted components included the TPU phone case and the rotating hub (printed in both TPU and PLA).

The PLA hub performed significantly better because its rigidity preserved the sharp edges of the detent recesses. TPU’s softness rounded the pockets and weakened the snapping action, so the PLA hub was used in the final assembly.

The three-screw constraint solved the torque-transfer problem entirely. The phone now rotated the hub reliably, engaging the detent mechanism with strong, consistent clicks.

## Conclusion

Through iterative CAD refinement and rapid 3D-printing cycles, the bike phone mount evolved into a reliable, robust system. Key lessons included: the importance of torque-transfer constraints between soft and rigid materials, the effect of spring strength on detent behavior, the need for careful tolerance adjustments for printed mechanisms, and how small geometric changes can dramatically improve performance.

The final assembly is stable, smooth, and secure—providing confident portrait/landscape rotation while maintaining durability during bike movement.

___

# Assembly and Use Instructions

1.	Identify the four main parts: the handlebar cuff, mount body, rotating hub, and phone case

2.	Install heat-set inserts:
- Insert two heat-set inserts into the openings on the handlebar cuff
- Insert three heat-set inserts into the designated pockets on the rotating hub

3.	Attach the mount body to the handlebar cuff:
-	Position the mount body on top of the handlebar cuff
- Align the screw holes and secure the two parts using an M5 × 12 mm screw (or the required screw count based on your design)

4.	Prepare the handlebar cuff for mounting:
-	Insert three M5 × 20 mm screws through the lower openings of the handlebar cuff
- Thread nuts onto the ends and tighten them finger-tight only for now

5.	Assemble the detent mechanism:
-	Insert the compression spring into the detent pocket located inside the recess of the mount body
- Place the ball bearing on top of the spring
-	Carefully position the rotating hub so the middle of the 5 cutouts aligns with the ball and press it into place

6.	Complete the rotation assembly:
-	Place the phone case on top of the rotating hub, making sure all screw holes align
- Insert an M5 × 20 mm screw through the center hole of the phone case, rotating hub, and mount body, and secure it on the otherside of the mount body with a nut
- Insert M5 × 8 mm screws into the remaining two holes and tighten

7.	Mount the assembly onto the bike:
-	Slide the handlebar cuff around the bike handlebar.
- Fully tighten the nuts on the three M5 × 20 mm screws using a wrench or pliers.

8.	Insert the phone:
-	•	Place your phone into the flexible TPU phone case

9.	Use the rotation feature:
-	Rotate the phone between portrait and landscape orientations
- The detent mechanism will snap cleanly into each locked position

---

# Bike Phone Mount Functioning 

<iframe width="560" height="315"
src="https://www.youtube.com/embed/p2g1acEJ3hk"
title="YouTube video player" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
allowfullscreen>
</iframe>

---

# Features

* **Functional Print-in-Place Joint Design:** The rigid plier arms are modeled with precise clearance at the pivot, enabling smooth rotation directly after printing. Joints were refined across iterations to minimize binding and reduce crunchy motion.
* **Reopening Spring Mechanism:** A TPU 95A flexible insert acts as a mechanical spring, automatically returning the pliers to their open state. Various thicknesses and geometries were tested to balance flexibility, durability, and comfortable operation.
* **Press-Fit Multi-Material Assembly:** While intended as a print-in-place device, the final design incorporates three components—two rigid handles and one TPU spring—assembled by hand without adhesives or tools. Press-fit mating was parameterized to achieve secure retention.

---

# Off-The-Shelf Parts

| Component                                                                 | Quantity |
|---------------------------------------------------------------------------|----------|
| TPU 95A Filament | Supplied in Lab |
| PLA Rigid Filament | Supplied in Lab |
| ABS Filament | Supplied in Lab
| m5x8mm Bolts | Supplied in Lab | 
| m5x12mm Bolts | Supplied in Lab | 
| m5x20mm Bolts | Supplied in Lab | 
| m5 Nuts | Supplied in Lab | 
| Pliers | Supplied in Lab
| Compression Spring | Supplied in Lab | 
| Ball Bearings | Supplied in Lab | 
| 3D Printer | Supplied in Lab |
| [Calipers](amazon.com/Neiko-01407A-Electronic-Digital-Stainless/dp/B000GSLKIW?crid=1C7BPKT5NIPWY&keywords=calipers&qid=1644422896&sprefix=calipers,aps,73&sr=8-4&th=1&linkCode=sl1&tag=drd0cf-20&linkId=73d2c46816e51f3eafe02410811438e6&language=en_US&ref_=as_li_ss_tl) | 1| 

---

# 3D Printed Parts

| 3D Printed Part | Purpose / Function |
|------------------|--------------------|
| Phone Case | Holds the phone securely and interfaces with the rotating hub |
| Rotating Hub | Provides the detent interface and rotates between portrait and landscape positions |
| Mount Body (Detent Enclosure) | Houses the detent mechanism and connects the rotating hub to the handlebar cuff |
| Handlebar Cuff | Clamps the entire assembly to the bike handlebar |

---

# CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811216d102bb630070b?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

---

{% include gallery caption="Multi Material Pliers Gallery" %}
