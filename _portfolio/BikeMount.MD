---
title: "Bike Phone Mount"
excerpt: "A custom set of multi-material pliers capable of gripping through-hole resistors, printed with an integrated flexible spring."
header:
  image: /assets/img/4 Pliers-Banner.JPG
  teaser: /assets/img/4 Pliers-Banner.JPG
gallery:
  - image_path: assets/img/4 Pliers-0.JPG
  - image_path: assets/img/4 Pliers-5.JPG
  - image_path: assets/img/4 Pliers-4.JPG
  - image_path: assets/img/4 Pliers-1.JPG
  - image_path: assets/img/4 Pliers-2.JPG
  - image_path: assets/img/4 Pliers-3.JPG
  - image_path: assets/img/4 Pliers-6.JPG
  - image_path: assets/img/4 Pliers-7.JPG
  - image_path: assets/img/4 Pliers-8.JPG
  - image_path: assets/img/4 Pliers-9.JPG
  - image_path: assets/img/4 Pliers-10.JPG
  - image_path: assets/img/4 Pliers-11.JPG
  
---

I designed and fabricated functional print-in-place needle-nose pliers using Fusion 360 and additive manufacturing. The device consists of two rigid arms and a flexible TPU spring element that returns the pliers to an open position when not in use. Through iterative prototyping and tolerance testing, I refined the spring geometry and press-fit interfaces to ensure smooth motion, reliable grip, and tool-free assembly. This project strengthened my skills in parametric CAD, mechanism design, and multi-material printing, resulting in a compact set of pliers suitable for handling small electronic components.

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

For the rotation interface, I used a simple detent mechanism because it was straightforward to understand and implement. The design relies on a spring-loaded ball engaging with angled recesses to create distinct snapping positions for portrait and landscape orientations. In practice, the mechanism works well and provides a clear locking feel that keeps the phone securely in place during rotation. The overall functionality, however, depends noticeably on the strength of the compression spring—stronger springs increase the locking force, while weaker ones make rotation easier but reduce the tactile feedback and stability.

I adjusted several dimensions to account for 3D-printing tolerances. Clearances for sliding and rotating features were increased slightly to prevent fused or overly tight fits after printing. The detent mechanism in particular required small adjustments to the recess depth and the diameter of the ball-bearing pocket so that the spring and ball could move freely without binding. I also added minor offsets around the phone-case contact surfaces to ensure the holder would grip securely without requiring post-processing. These small dimensional changes helped the printed parts function smoothly right off the printer.

I used FFF (fused filament fabrication) printing for all components because it allowed quick iteration, good dimensional control, and compatibility with the screws and heat-set inserts used throughout the design. The meltable thermoplastics made it easy to embed inserts cleanly and achieve strong threaded connections. Multiple materials were used based on the mechanical needs of each part. ABS was chosen for the hook component that clamps around the handlebar due to its higher toughness and heat resistance. PLA was used for the structural stand connecting the detent mechanism to the handlebar attachment as well as for the detent mechanism itself, since these parts needed good dimensional accuracy and rigidity. TPU was used for the phone holder portion because its flexibility provides a secure, cushioned grip on the phone while preventing scratches and reducing vibration.

# Assembly and Use Instructions

1.	Identify the four main parts: the bike cuff, phone stand/enclosure, rotator, and phone case.

2.	Install heat-set inserts:
- Place inserts into the two top openings of the bike cuff.
- Place inserts into the three openings in the rotator.

3.	Attach the phone stand to the bike cuff:
-	Position the phone stand in the top opening of the bike cuff.
-	Align the screw openings and secure them using an M5 × 12 mm screw.

4.	Prepare the bike cuff for mounting:
-	Insert three M5 × 20 mm screws through the bottom openings of the bike cuff.
-	Add nuts on the opposite side and tighten only finger-tight for now.

5.	Assemble the detent mechanism:
-	Insert the compression spring into the detent pocket inside the square recess of the connector piece.
-	Place the ball bearing on top of the spring in the circular pocket.
-	Carefully position the rotating center piece so the cutout aligns with the ball and press it into place.

6.	Complete the rotation assembly:
-	Place the phone case component on top and align all screw holes.
-	Insert an M5 × 12 mm screw through the center hole and secure it with a nut.
-	Insert M5 × 8 mm screws into the remaining two openings and tighten.

7.	Mount onto the bike:
-	Fit the circular cuff around the handlebar.
-	Fully tighten the nuts with a wrench or pliers to secure the assembly.

8.	Insert the phone:
-	Place your phone into the flexible TPU phone case.

9.	Use the rotation feature:
-	Rotate the phone between portrait and landscape orientations; the detent mechanism will snap it into position.

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

| 3D Printed Part        | Purpose / Function |
|-------------------------|--------------------|
| Phone Case     | Securely hold the phone |
| Detent Mechanism    | Allows for rotation of the phone case |
| Detent Enclosure / Phone Stand | Support the phone with enough space to turn on top of the bike handles and enclose the detent mechanism | 
| Bike Cuff | Secure the entire assembly to the bike handles | 

---

# CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811467bd955eaef8446?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>


---

{% include gallery caption="Multi Material Pliers Gallery" %}
