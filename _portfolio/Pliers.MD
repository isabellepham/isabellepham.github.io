---
title: "MultiMaterial Pliers"
excerpt: "A custom set of multi-material pliers capable of gripping through-hole resistors, printed with an integrated flexible spring."
header:
  image: /assets/img/4 Pliers-Banner.JPG
  teaser: /assets/img/4 Pliers-Banner.JPG
gallery:
  - image_path: assets/img/4 Pliers-0.JPG
  - image_path: assets/img/4 Pliers-1.JPG
  - image_path: assets/img/4 Pliers-2.JPG
  - image_path: assets/img/4 Pliers-3.JPG
  - image_path: assets/img/4 Pliers-4.JPG
  - image_path: assets/img/4 Pliers-5.JPG
  - image_path: assets/img/4 Pliers-6.JPG
  - image_path: assets/img/4 Pliers-7.JPG
  - image_path: assets/img/4 Pliers-8.JPG
  - image_path: assets/img/4 Pliers-9.JPG
  - image_path: assets/img/4 Pliers-10.JPG
  - image_path: assets/img/4 Pliers-11.JPG
  
---

I designed and fabricated functional print-in-place needle-nose pliers using Fusion 360 and additive manufacturing. The device consists of two rigid arms and a flexible TPU spring element that returns the pliers to an open position when not in use. Through iterative prototyping and tolerance testing, I refined the spring geometry and press-fit interfaces to ensure smooth motion, reliable grip, and tool-free assembly. This project strengthened my skills in parametric CAD, mechanism design, and multi-material printing, resulting in a compact set of pliers suitable for handling small electronic components.

---
# Print-in-Place
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Preform external research to determine other applications print-in-place has been used.
</p>

Print-in-Place design is the process of 3D printing fully functional, multi-material mechanisms in a single print. By incorporating clearances and detailed fabrication between moving parts, Print-in-Place models are intended to be ready to move, rotate, or flex after being removed from the print bed. This technique demonstrates the potential of additive manufacturing to produce mechanical assemblies efficiently and reduce the need for external fasteners or manual labor. 

A common application of print-in-place design is in hinges and articulated joints, which can be found in foldable lids or doors. Designers can create these by modeling living or geared hinges with carefully tuned clearances so motion is achieved immediately after printing. This capability—producing movable joints directly from additive manufacturing processes without assembly—has been the focus of multiple engineering studies. For example, [Song and Chen (2012)](https://www.researchgate.net/publication/267490468_Joint_Design_for_3-D_Printing_Non-Assembly_Mechanisms?enrichId=rgreq-1843d6d0d90a7a5da64354c5817ecba1-XXX&enrichSource=Y292ZXJQYWdlOzI2NzQ5MDQ2ODtBUzo1NjUzNDMzMjE5NDQwNjRAMTUxMTc5OTc1OTIzMQ%3D%3D&el=1_x_2)  demonstrated how joint geometry can be optimized to overcome fabrication limitations in 3D-printed non-assembly mechanisms. Their research introduced a marker-based joint design to minimize excessive joint clearance caused by the limited accuracy of stereolithography (SLA) printing, enabling smoother rotational motion in cylindrical pin joints built as single prints. They found that these geometrically modified joints could achieve smaller clearances and improved rotational stability compared to traditional pin joints, validating the potential of print-in-place manufacturing for hinges and other movable subsystems.

Print-in-Place is also widely applied in the creation of parts that combine rigid structural elements with flexible features, like the pliers I created or tools, grips, and integrated springs. Designers model the irgid body for load-bearing or shape definition and add flexible zones. A dual-extrusion or multi-material printer would be needed to deposit both materials in a single print job. The result is a fully functional assembly in one go. [Ermolai et al. (2022)](https://www.researchgate.net/publication/365220539_Design_and_Testing_of_Multi-Material_Shape-Changing_Flexure_Hinges_for_Fused_Filament_Fabrication) demonstrate this concept through their study of multi-material flexure hinges printed via Fused Filament Fabrication. In their work, rigid bodies were printed in ABS or PLA, while the flexible hinge sections were printed in a thermoplastic co-polyester (TPC), producing fully functional hinges with corrugated or shape-changing interfaces. Their results validate the feasibility of print-in-place multi-material parts, illustrating how designers can achieve embedded flexible features—like springs or compliant joints—without post-processing or assembly, closely aligning with the creation of functional tools and grips in one print.


<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">

What combination of materials work well for print-in-place?
</p>

In Fused Filament Fabrication (FFF) or FDM printing, common combinations include: 
- PLA with TPU or TPE
- ABS with TPU or TPC
- PETG with TPU 
- Nylon with TPU

PLA paired with TPU or TPE is easy to print and suitable for low-stress hinges, grips, and flexible joints, although the interface can be sensitive to cooling and may require fine-tuning. ABS combined with TPU or TPC provides higher strength and better thermal resistance, making it ideal for functional springs or hinges under repeated loads, as demonstrated in Ermolai et al. (2022). PETG with TPU is effective for snap-fit enclosures with soft seals, while Nylon with TPU offers exceptional toughness for parts subjected to repeated flexing, though it requires careful humidity control and bed adhesion.

For high-resolution SLA, DLP, or PolyJet printing, rigid resins can be paired with elastic or flexible resins to create compliant hinges, soft grips, or embedded seals. PolyJet technology, in particular, allows mixing materials within a single layer for smooth transitions between rigid and flexible zones. Using tough or engineering resins in combination with flexible resins can yield high-strength parts with embedded springs, living hinges, or gaskets.

# Design and Iterative Process
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
About the design and iterative process (e.g., how was the spring component created and how is it retained in the model, materials used)
</p>

The design and iterative process for the pliers began in Fusion 360, using CAD tools to streamline modeling and reduce sketching time. For the first iteration, I based the design on plier examples from the digital fabrication lab and utilized mirroring to efficiently replicate features. I extruded 5 mm and separated each functional element into its own body: the center flexible square, handle 1, handle 2, jaw 1, and jaw 2. The handles and jaws were printed in PLA, while the flexible center was printed in TPU. Initial prints of the TPU center revealed several issues: the small straight features of the gridding were extruding as thin lines due to the original print speed of 100 mm/s, resulting in poor welding. Additionally, the square in CAD was not rotated to the correct angle, causing the grid pattern to flex incorrectly. Adjustments in slicer, including reducing the print speed to 30 mm/s and changing the infill angle to 0°, resolved these problems. I also experimented with different infill densities for the center to fine-tune flexibility. Once these errors were addressed, the first complete assembly functioned, successfully picking up resistors, though the thinness of the pliers made them uncomfortable to hold and the edges of the handles detached from the center square more than desired.

For the next iteration, I refined the design to improve comfort, functionality, and connectivity. Using calipers to measure real pliers in the lab, I extruded the handles to 13 mm and shortened the length of both the handles and jaws to localize movement. To strengthen the joints, I extended the edges of the handles and jaws to make contact with the center square rather than ending at the last trapezoid in the joint. Additionally, I added a flat edge at the end of the jaws to stabilize the pliers when picking up items. This iteration proved more comfortable to hold and better at handling resistors. The only remaining design consideration was the bulkiness of the jaws due to the 13 mm handle thickness; while functional, a thinner jaw would improve aesthetics without compromising usability. I also should have filleted the handles more so that the edges were not sharp to the user's hand. 


# Specifications of the Pliers

The pliers consist of a center flexible square measuring 25 mm by 25 mm, which serves as the core spring element. Attached to each side of the square are three trapezoids forming dovetail-style joints, designed to connect the handles and jaws securely. Each trapezoid features two 55° angles, a longer edge of 5 mm, a shorter edge of 1.5 mm, and a height of 2.5 mm. The jaws extend 55 mm in length, with a flat edge of 44 mm at the tip to provide stability when picking up items. The handles, where the user grips the pliers, are 65 mm in length, providing adequate leverage and comfort for manipulation. These specifications were carefully chosen to balance flexibility, strength, and ergonomic usability.

# Print Settings

For the pliers, two separate printers and material setups were used to optimize the rigid and flexible components. The center flexible square was printed in TPU using a printer equipped with a 4 mm nozzle, which allowed for precise detail and sharp features in the dovetail joints. The print speed was reduced to 30 mm/s to ensure proper extrusion and layer adhesion. Prior to printing, the top and bottom layers of the square were removed in the slicer to expose the infill, which was set to a “grid” pattern with 18% density and a 0° orientation to maximize flexibility along the intended bending direction. The handles and jaws were printed in PLA on a separate printer with a 6 mm nozzle. These rigid components did not require adjustment to the default print settings, as PLA’s properties and the nozzle size were sufficient to produce the desired strength and dimensional accuracy.

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
| 3D Printer | Supplied in Lab |
| [Calipers](amazon.com/Neiko-01407A-Electronic-Digital-Stainless/dp/B000GSLKIW?crid=1C7BPKT5NIPWY&keywords=calipers&qid=1644422896&sprefix=calipers,aps,73&sr=8-4&th=1&linkCode=sl1&tag=drd0cf-20&linkId=73d2c46816e51f3eafe02410811438e6&language=en_US&ref_=as_li_ss_tl) | 1| 

---

# 3D Printed Parts

| 3D Printed Part        | Purpose / Function |
|-------------------------|--------------------|
| Handle and Jaws v1     | Initial iteration for fit testing |
| Handle and Jaws v2+ | Refined design with adjusted dimensions | 
| TPU Flexible Component | Flexibility and spring constant testing | 

---

# CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811467bd955eaef8446?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

---

# How to Operate the Multi-Material Pliers
1. Position the tips around the intended object to be picked up.
2. Squeeze the handles to close the jaws. 
3. Lift pliers and object from original position and move to final position. 
4. Release pressure to allow the spring to reopen and release the object. 

---

{% include gallery caption="Multi Material Pliers Gallery" %}
