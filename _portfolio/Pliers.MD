---
title: "MultiMaterial Pliers"
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
# Print-in-Place
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Preform external research to determine other applications print-in-place has been used. What combination of materials work well for print-in-place?
</p>

Print-in-Place design is the process of 3D printing fully functional, multi-material mechanisms in a single print. By incorporating clearances and detailed fabrication between moving parts, Print-in-Place models are intended to be ready to move, rotate, or flex after being removed from the print bed. This technique demonstrates the potential of additive manufacturing to produce mechanical assemblies efficiently and reduce the need for external fasteners or manual labor. 

A common application of print-in-place design is in hinges and articulated joints, which can be found in foldable lids or doors. Designers can create these by modeling living or geared hinges with carefully tuned clearances so motion is achieved immediately after printing. This capability—producing movable joints directly from additive manufacturing processes without assembly—has been the focus of multiple engineering studies. For example, [Song and Chen (2012)](https://www.researchgate.net/publication/267490468_Joint_Design_for_3-D_Printing_Non-Assembly_Mechanisms?enrichId=rgreq-1843d6d0d90a7a5da64354c5817ecba1-XXX&enrichSource=Y292ZXJQYWdlOzI2NzQ5MDQ2ODtBUzo1NjUzNDMzMjE5NDQwNjRAMTUxMTc5OTc1OTIzMQ%3D%3D&el=1_x_2)  demonstrated how joint geometry can be optimized to overcome fabrication limitations in 3D-printed non-assembly mechanisms. Their research introduced a marker-based joint design to minimize excessive joint clearance caused by the limited accuracy of stereolithography (SLA) printing, enabling smoother rotational motion in cylindrical pin joints built as single prints. They found that these geometrically modified joints could achieve smaller clearances and improved rotational stability compared to traditional pin joints, validating the potential of print-in-place manufacturing for hinges and other movable subsystems.

Print-in-Place is also widely applied in the creation of parts that combine rigid structural elements with flexible features, like the pliers I created or tools, grips, and integrated springs. Designers model the irgid body for load-bearing or shape definition and add flexible zones. A dual-extrusion or multi-material printer would be needed to deposit both materials in a single print job. The result is a fully functional assembly in one go. [Ermolai et al. (2022)](https://www.researchgate.net/publication/365220539_Design_and_Testing_of_Multi-Material_Shape-Changing_Flexure_Hinges_for_Fused_Filament_Fabrication) demonstrate this concept through their study of multi-material flexure hinges printed via Fused Filament Fabrication. In their work, rigid bodies were printed in ABS or PLA, while the flexible hinge sections were printed in a thermoplastic co-polyester (TPC), producing fully functional hinges with corrugated or shape-changing interfaces. Their results validate the feasibility of print-in-place multi-material parts, illustrating how designers can achieve embedded flexible features—like springs or compliant joints—without post-processing or assembly, closely aligning with the creation of functional tools and grips in one print.

In Fused Filament Fabrication (FFF) or FDM printing, common combinations include: 
- PLA with TPU 
- PLA with PVA (water soluble supports)
- ABS and HIPs
- Fresh and recycled material 

PLA paired with TPU or TPE is common because PLA provides a stiff, precise structural frame while TPU/TPE adds flexible, rubber-like joints, allowing immediate motion after printing without assembly. PLA with PVA is widely used for complex interlocking parts since PVA serves as a water-soluble support material that can be removed cleanly after printing, freeing moving components without damage. 

ABS and HIPS are another compatible pair, where ABS offers strong, heat-resistant structures and HIPS can be dissolved in a solvent like d-limonene, making it ideal for internal supports in high-temperature PIP parts. Finally, combining fresh and recycled materials allows designers to balance printability, strength, and sustainability, with fresh filament ensuring reliable extrusion and structural integrity while recycled filament reduces waste, making it suitable for non-critical sections of functional assemblies.

The inter- and intra- layer bonding of two separate plastics depnds on the materials' surface energy, chemical composition, shrinkage and cooling rates, and mechanical compatibility. 

# Design and Iterative Process
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
About the design and iterative process (e.g., how was the spring component created and how is it retained in the model, materials used)
</p>

The design and iterative process for the pliers began in Fusion 360, using CAD tools to streamline modeling and reduce sketching time. For the first iteration, I based the design on plier examples from the digital fabrication lab, using them as a reference to ensure proper ergonomics and functional dimensions. While sketching in Fusion 360, I utilized the mirroring tool to efficiently replicate symmetric features, which reduced the number of individual constraints required and helped maintain geometric consistency across the model. I extruded each component to 5 mm and separated each functional element into its own body: the center flexible square, handle 1, handle 2, jaw 1, and jaw 2. This separation allowed me to assign different materials and print settings to each part, an essential consideration for multi-material print-in-place designs.

For printing, I sliced the two handles and two jaws together for PLA without modifying any print settings, since PLA is a relatively rigid and reliable material. I sliced the flexible square separately for TPU, removing the top and bottom solid layers of the horizontal shells and changing the infill type to "rectilinear." This approach was intended to reduce material use while maintaining sufficient flexibility.

The initial print of the handles and jaws was successful in achieving what I CAD-ed. 

<p align="center">
  <img src="/assets/img/4 Pliers-Figure0.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 1. First Iteration of the PLA Handles and Jaws</em>
</p>

However, the TPU center presented multiple challenges. The first print suffered from significant stringing and under-extrusion, which compromised the structural integrity of the flexible square.

<p align="center">
  <img src="/assets/img/4 Pliers-Figure1.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 2. Printing Problems with the Center Flexible Square (Iteration 1 and 2)</em>
</p>

After reflecting on the in-class walk through of how to slice the flexible material by varying the infill, I realized that the infill type should be "grid." Rectalinear meant that the extruded filament was printed in only one direction per layer, rotating 90° for the next, which left gaps between each layer and reduced the structure's strength. Grid infill prints lines in both the X and Y directions on the same layer which is better for supporting the top surfaces and achieving higher strenght. This iteration looked better than the previous but I was still experiencing a lot of stringing. 

<p align="center">
  <img src="/assets/img/4 Pliers-Figure2.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 3. Flexible Square with Grid Infill (Iteration 3)</em>
</p>

After reflecting on the in-class demonstration of slicing flexible materials with varying infill patterns, I realized that the "rectilinear" infill was suboptimal. Rectilinear prints filament lines in one direction per layer, rotating 90° for the next, which leaves gaps between layers and reduces strength. I switched the infill to "grid," which prints lines in both X and Y directions on the same layer, providing better support for the top surfaces and increasing structural integrity. This adjustment improved the print visually and mechanically, but stringing persisted.

To address the remaining stringing issues, I researched best practices for TPU printing and found that print speed significantly affects filament flow and cooling. By reducing the printer speed from 100 mm/s to 30 mm/s, the extruded filament had sufficient time to flow, bond, and solidify, reducing stringing dramatically. This modification produced a clean, functional flexible square.

<p align="center">
  <img src="/assets/img/4 Pliers-Figure3.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 4. Flexible Square with Grid Infill and Decreased Print Speed (Iteration 4) </em>
</p>

During the first functional test, I discovered that the pliers’ motion was constrained. This issue arose because the infill angle was still set to the slicer default of 45°, which did not align with the direction of flex needed for the pliers. Adjusting the infill angle to 0° ensured that the flexible square could bend properly along the intended axis, allowing the pliers to achieve the desired movement. 

After resolving the printing errors and infill angle issues, I printed three flexible squares simultaneously, each with different infill densities: 13%, 18%, and 23%. This allowed me to compare the flexibility and structural integrity of each variation under identical print conditions.

<p align="center">
  <img src="/assets/img/4 Pliers-Figure4.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 5. Flexible Square with Varied Infill Density (Iteration 5, 6, and 7) </em>
</p>

I decided that 18% was an appropriate infill density for the flexibility and range of motion I desired for my pliers. I assembled the pliers by pushing the handles and jaws into the dovetail joints or trapezoids off of the square. 

<p align="center">
  <img src="/assets/img/4 Pliers-Figure5.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 6. Assembled Pliers </em>
</p>

After testing, I determined that 18% infill provided the ideal balance between flexibility and stability for the range of motion I wanted. The lower density (13%) was overly flexible and failed to support the weight of the handles, while the higher density (23%) restricted motion and made the pliers too rigid. Once the flexible square was finalized, I assembled the pliers by inserting the handles and jaws into the dovetail (trapezoidal) joints extending from the square.

The first assembled iteration was functional—the pliers were capable of picking up multiple resistors. However, several ergonomic and structural limitations became apparent. The handles were too thin, making them uncomfortable to grip during repeated use, and the long jaws created an unstable feel by increasing the distance between the user’s motion and the gripping tips. Additionally, when the handles were flexed, the edges connecting to the dovetail joints began to separate, nearly detaching from the flexible square. This indicated that the contact area between the rigid and flexible materials was insufficient for the applied bending forces.

<p align="center">
  <img src="/assets/img/4 Pliers-Figure6.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 7. Close up of Dovetail Joints between the Flexible Square and Handles </em>
</p>

For the next iteration, I focused on improving comfort, functionality, and connectivity between components. Using calipers to measure standard pliers in the lab, I increased the overall extrusion thickness from 5 mm to 13 mm for greater durability and user comfort. I also shortened both the handles and jaws to localize movement, reducing the lever arm and improving control. Additionally, I incorporated a flat edge at the end of the jaws to stabilize the pliers when gripping objects on a flat surface. This iteration felt more ergonomic and performed better during testing—it was able to securely pick up resistors without excessive bending or slippage.

To strengthen the joints, I extended the handle and jaw edges so they directly contacted the center flexible square, rather than ending at the final trapezoid of the dovetail joint. This adjustment distributed stress more evenly and reduced the likelihood of separation under repeated flexing.

<p align="center">
  <img src="/assets/img/4 Pliers-Figure7.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 8. Changes to the Joints between the Handles, Jaws to the Center Square in Fusion </em>
</p>

The final assembly was significantly more comfortable and demonstrated smoother articulation. The shortened handles allowed for a greater range of motion, increasing mechanical advantage and precision. During in-class testing, I was able to pick up 10 resistors in 30 seconds.

<p align="center">
  <img src="/assets/img/4 Pliers-Figure8.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 9. Final Assembly of Multi-Material Pliers </em>
</p>

Looking ahead, several refinements could further enhance performance and usability. While the 13 mm handle thickness improved comfort, it made the jaws appear bulky; a slightly thinner jaw design could improve aesthetics without sacrificing functionality. The addition of the flat edge at the jaw tips was helpful for stability but limited the ability to grip objects at non-perpendicular angles. Drawing inspiration from needle-nose pliers could solve this issue by tapering the jaw shape. Additionally, filleting the handle edges more generously would prevent discomfort from sharp corners during prolonged use.

Overall, this project taught me the value of rapid iteration and the importance of systematically diagnosing issues related to both CAD design and print parameters. I gained a deeper understanding of how factors such as infill type, density, and print speed influence the mechanical behavior of multi-material, print-in-place assemblies.

# Specifications of the Pliers

The pliers feature a central flexible square measuring 25 mm × 25 mm, which functions as the core spring element enabling the pliers’ motion. The internal grid infill pattern is set to 18% density, providing the optimal balance between flexibility and structural stability.

Each side of the flexible square includes three trapezoidal extensions that form dovetail-style joints, designed to securely attach the handles and jaws while allowing limited rotational movement. Each trapezoid measures 5 mm along the longer edge, 1.5 mm along the shorter edge, with a height of 2.5 mm, and two 55° angled sides to ensure a snug mechanical fit. The spacing between trapezoids varies depending on function—1.5 mm apart on the sides connecting to the jaws for tighter control and 1.2 mm apart on the sides connecting to the handles to allow slightly greater flexibility during user operation.

The jaws extend 55 mm in length and terminate in a 4 mm flat edge, which provides surface stability when gripping flat objects such as resistors. The handles, designed for comfortable and controlled user grip, measure 65 mm in length, offering sufficient leverage without excessive strain. The entire assembly maintains a uniform 13 mm thickness.

<p align="center">
  <img src="/assets/img/4 Pliers-Figure9.jpeg" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 10. Dimensions of the Pliers Sketch in Fusion </em>
</p>

# Print Settings

For the pliers, two separate printers and material setups were used to optimize the rigid and flexible components. The center flexible square was printed in TPU using a printer equipped with a 4 mm nozzle, which allowed for precise detail and sharp features in the dovetail joints. The print speed was reduced to 30 mm/s to ensure proper extrusion and layer adhesion. Prior to printing, the top and bottom layers of the square were removed in the slicer to expose the infill, which was set to a “grid” pattern with 18% density and a 0° orientation to maximize flexibility along the intended bending direction. The handles and jaws were printed in PLA on a separate printer with a 6 mm nozzle. These rigid components did not require adjustment to the default print settings, as PLA’s properties and the nozzle size were sufficient to produce the desired strength and dimensional accuracy.

<p align="center">
  <img src="/assets/img/4 Pliers-5.JPG" alt="Print Failure" width="600"/>
  <br>
  <em>Figure 11. 3D Printer Creating Iterations of the Flexible Square </em>
</p>

# Pliers Functioning 

<iframe width="560" height="315"
src="https://youtube.com/shorts/jAHtPoRO1sw?feature=share"
frameborder="0" allowfullscreen></iframe>

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
