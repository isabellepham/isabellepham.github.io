---
title: "uFluidic Device"
excerpt: "This microfluidic device leverages laminar flow principles to separatae particles by size using a custom-designed pinch flow fractionation (PFF) chip!"
header:
  image: assets/img/3 uFluidic Device-Banner.JPG
  teaser: assets/img/3 uFluidic Device-Banner.JPG
gallery:
  - image_path: assets/img/3 uFluidic Device-1.JPG
  - image_path: assets/img/3 uFluidic Device-2.JPG
  - image_path: assets/img/3 uFluidic Device-6.JPG
  - image_path: assets/img/3 uFluidic Device-3.JPG
  - image_path: assets/img/3 uFluidic Device-4.JPG
  - image_path: assets/img/3 uFluidic Device-5.JPG

---

I created a microfluidic pinch flow fractionation (PFF) device that separates particles of different sizes using controlled laminar flow. The process involved modeling the mold in Autodesk Fusion 360, resin printing it with a Form 3 SLA printer, casting the device in PDMS, and sealing it with glass before testing its ability to sort microspheres into separate outlets.

Unlike filtration-based separation methods, PFF allows for continuous and gentle particle sorting, making it useful in biomedical research, diagnostics, and materials science. This project combined CAD design, precision fabrication, and experimental testing to explore the physics of microscale flow and particle behavior.

---

# Introduction 

# Pinch Flow Fractionation?
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
What is Pinch Flow Fractionation? How does it work?
</p>

Pinched Flow Fractionation (PFF) is a microfluidic technique used to separate particles based on their size without the need for external or active fields such as electric or magnetic forces. The PFF device consists of two main regions: a pinched section and a broad section.

The pinched section is a narrow channel where a sample stream containing particles, and a buffer stream enter simultaneously. The buffer flow “pinches” the particle containing stream tightly against one wall of the channel which aligns all particles, regardless of size, to move near the same wall. As the solution enters the broad section, the channel widens, and the streamlines separate.  

Due to laminar flow, particles maintain their relative positions meaning larger particles stay closer to the centerline, while smaller ones stay closer to the wall. This displacement allows different-size particles to be continuously sorted and collected through different outlet channels. 

# Application of PFF for sorting small particles 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Provide at least one specific application that requires sorting small particles. Benefits of PFF over traditional techniques (e.g., filters) for sorting this particle? Include at least one citation from primary literature. Citation should be hyperlinked. 
</p>

One important application of Pinched Flow Fractionation (PFF) is the separation of circulating tumor cells (CTCs) from whole blood for cancer diagnosis and monitoring. This process directly involves sorting small particles, as it operates at the microscale, handling biological components that range from a few micrometers to nanometers in size. CTCs are typically 10–20 µm in diameter, compared to 6–8 µm for red blood cells, and these subtle size differences are crucial for effective separation within microfluidic channels.

CTCs are rare cells shed from primary tumors into the bloodstream, and their efficient isolation is important for early detection and treatment planning. They are believed to be the main cause of cancer-related fatalities and serve as valuable biomarkers. To use CTCs effectively, they must be efficiently separated from the complex mixture of blood cells and plasma. 

Traditional methods like gel electrophoresis or centrifugation often led to cell deformation, clogging, and low recovery rates due to mechanical stress and sample loss. PFF is beneficial in this application because it enables gentle, continuous, and label-free separation of CTCs based purely on intrinsic differences in size and deformability. This method enables noninvasive isolation of cancer cells and minimizes sample loss while preserving cell viability for downstream molecular analysis. 

--- 

# Design 

# Asymmetric Approach 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Did you choose a symmetric or asymmetric approach? 
</p>

I chose an asymmetric design for the Pinched Flow Fractionation (PFF) device. In this configuration, the outlet channels and flow paths are not mirror images of each other, and the device geometry intentionally differs across outlets to achieve flow balancing and particle separation efficiency. The asymmetry arises primarily from the differences in outlet widths, channel lengths, and outlet positions. Each outlet was dimensioned according to its expected flow fraction and target hydraulic resistance: the buffer outlet was made wider and shorter to accommodate the highest flow rate, while the large and small particle outlets were progressively narrower and longer to restrict flow and maintain balanced pressure drops.

This asymmetric approach ensures that each outlet experiences a controlled pressure differential, allowing the device to separate particles by size without cross-contamination. It also provides greater flexibility in tuning flow distribution compared to a symmetric layout, which typically assumes equal outlet resistances and is less effective when the outlets handle significantly different flow volumes, as in this design.

# Outlet Boundaries 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
How did you decide where to place the outlet boundaries for small particles, large particles, and buffer flow? 
</p>

To determine the outlet positions, I used the algebraic relationship that describes the streamline position of particles exiting the pinched section. 
$$
Y_0 = (w_p - \frac{D}{2}) \left(\frac{w_b}{w_p}\right)
$$
Where: 

w_p = width of the pinched segment

w_b = width of the broadened segment

D = particle diameter 

For context, the pinched segment width was calculated based on the design guideline that it should be 1.2–1.5 times the diameter of the largest particle to prevent clogging while maintaining effective flow focusing. Given the largest particle diameter of 500 µm, wp = 1.2 to 1.5 x 500 µm = 600 to 750 µm. A midpoint value of 650 µm (0.65 mm) was chosen for stability and manufacturability. 

The broad section was designed to be as wide as possible without interfering with the bonding buffer, which must remain 3 mm from the device edge to ensure proper sealing. Extending 20 mm from either side of the end of the pinched channel resulted in an overall broad section width of 40.65 mm.

In this context, “the wall” refers to the bonding buffer boundary, located 3 mm from the inner edge of the device base wall. 

To determine the outlet positions, I applied the PFF streamline equation using the calculated values for the pinched width (wp=0.65) and broad section width (wb=40.65). 

For the large particle outlet, substituting particle diameters of 500 µm and 425 µm into the equation gave Y0 values of 25.02 mm and 27.05 mm, respectively. Averaging these results yielded a final outlet position of approximately 26.03 mm from the wall. 

For the small particle outlet, using diameters of 150 µm and 125 µm produced Y0 values of 35.96 mm and 36.74 mm, respectively, which averaged to 36.35 mm from the wall. 

The buffer outlet was positioned 10 mm from the wall, allowing sufficient separation from the large particle stream while providing additional space for a larger outlet diameter and lower hydraulic resistance. 

This configuration ensures that the buffer channel carries the majority of the flow, while the large and small particle outlets collect their respective size fractions with minimal cross-contamination. For simplicity and manufacturability in the CAD model, these outlet positions were rounded to 10 mm for the buffer outlet, 26 mm for the large particle outlet, and 37 mm for the small particle outlet (to ensure the 11 mm minimum between each outlet was abided by).

Once the outlet centers were established, I defined the boundaries (or openings) of each outlet channel by calculating the midpoints between adjacent outlet centers. This ensured that each particle size would exit through its intended channel without overlapping flow regions. For example, the midpoint between the large particle outlet (26 mm) and the small particle outlet (37 mm) is 31.5 mm. Thus, the end of the small particle channel, representing its outer boundary, was set at 31 mm from the wall. Therefore, it spans from 31 mm to 42.325 mm (where the broad section edge is). 

Similarly, the large particle channel was defined from 18 mm to 31.5 mm, where 18 mm is the midpoint between the large particle outlet (26 mm) and the buffer outlet (10 mm). Finally, the buffer channel occupies the region from the wall (0 mm reference) to approximately 18 mm, capturing the particle-free fluid layer near the channel boundary.

This approach, using outlet midpoint spacing, ensures consistent separation zones that match the streamline distribution observed in PFF theory. It also helps minimize cross-contamination between particle fractions while maintaining balanced hydraulic resistance across the three outlets.

# Flow Balancing Problem 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
How did you attempt to solve the flow balancing problem discussed in the beginning of the assignment details document? 
</p>

The flow balancing problem in Pinched Flow Fractionation (PFF) arises when outlet channels have unequal hydraulic resistances, causing the fluid to distribute unevenly among the outlets. Because the buffer outlet must carry a significantly larger portion of the total flow, it naturally experiences a higher flow rate. If all outlets were identical in length and width, this imbalance could cause fluid from one flow region (e.g., the large particle stream) to divert into another outlet, reducing sorting accuracy and increasing cross-contamination.

To address this, I varied both the outlet widths and lengths to generate controlled hydraulic resistance that balances flow across all three outlets. This design approach is based on the principle that hydraulic resistance increases with channel length and decreases with the cube of its width. In other words, longer and narrower channels restrict flow more, while wider and shorter ones allow higher flow rates.

I began by assigning entrance widths proportional to the expected outlet flow fractions: 2.20 mm for the buffer outlet (highest flow), 1.50 mm for the large particle outlet, and 0.60 mm for the small particle outlet (lowest flow). Using the buffer channel (18 mm long) as the baseline, I scaled the other outlet lengths to maintain approximately equal pressure drops. The width ratio between the buffer and large particle outlets is 2.20/1.50 = 1.47, giving a large particle channel length of 18×1.47 = 26.4 mm. Similarly, the width ratio between the buffer and small particle outlets is 2.20/0.60 = 3.67, resulting in a small particle channel length of 18×3.7 = 66.6 mm.

Because these calculated lengths exceeded the available footprint of the uFluidic mold, I implemented serpentine outlet channels to achieve the required effective lengths within the compact device geometry. The serpentine layout preserves laminar flow while fitting long channels into limited space. All corners were filleted to minimize local turbulence, maintain stable flow paths, and avoid particle trapping.

The detailed layout of each serpentine, such as the height of vertical legs, horizontal offsets, and number of bends, was determined through iterative design and trial-and-error adjustments in CAD. I began by dividing the available device area by the target channel length to estimate the number of turns required, then fine-tuned the path to achieve the correct total length while maintaining safe spacing between adjacent bends. This spacing prevents channels from touching or merging during fabrication, reduces print errors, and maintains consistent hydraulic resistance across all outlets.

# Potential Future Changes to Outlet Geometry 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
What would you change about your outlet geometry if you could iterate on this design? 
</p>

I would mainly aim to replace my trial-and-error fine tuning with a more target-drive and mathematical approach. Perhaps I would pick the desired flow split between outlets first, convert that to target resistances, and then solve for the required channel lengths using geometry. This would reduce iteration and provide a clearer template of what would need to be implemented in CAD. 

Another way I would iterate on this design is using height as another way to adjust resistance. Changing the channel depth or height locally can create large resistance without extreme lengths. Increasing or decreasing height is also more compact than extreme serpentine lengths and easier to fabricate than extra bends. 

---

# Parylene Coating and Hypothetical Applications 

Resin-printed molds are coated with parylene before PDMS casting to create a thin, inert, and hydrophobic barrier that prevents unwanted chemical and mechanical interactions between the mold and the polymer. Without this coating, the PDMS can adhere to or react with the uncured resin surface, leading to defects such as tearing, warping, or incomplete demolding. The parylene layer serves as both a release agent and a chemical barrier, enabling the PDMS to cure properly and release cleanly while preserving the fine surface features of the mold. Additionally, the parylene coating improves the dimensional stability and surface smoothness of the printed mold, which is essential for maintaining laminar flow and accurate channel geometry in microfluidic applications.

This PFF-based microfluidic sorter has a wide range of potential applications. In biomedical diagnostics, it could be used to isolate circulating tumor cells (CTCs) or exosomes from blood for cancer detection and monitoring. In environmental science, it could separate microplastics, bacteria, or other particulates from water samples for pollution analysis. Similarly, in materials research, the device could sort polymer microspheres or nanoparticles by size for manufacturing and coating processes. In cell biology, the same sorting principle could be applied to separate cells, vesicles, or organelles based on size or deformability, enabling single-cell analysis and other downstream studies.

# Geometry Relation to Sorting 

The geometry of my uFluidic device was carefully designed to support precise size-based separation consistent with Pinched Flow Fractionation (PFF) theory. The pinched region width (wp = 0.65 mm) was selected to be approximately 1.3 times the diameter of the largest particle (500 µm) to ensure effective focusing of particles against the wall without causing clogging. This confinement forces all particles into a narrow, well-defined region, aligning them along the same streamline before entering the broad section. The broad region width (wb = 40.65 mm) represents a roughly 62.5× expansion relative to the pinched width, allowing for significant streamline divergence and clear spatial separation between particles of different diameters as they flow outward.

Outlet positions were determined using the PFF streamline equation to ensure that each size fraction exited through the correct channel with minimal cross-contamination. The buffer outlet was placed 10 mm from the wall, the large particle outlet at 26 mm, and the small particle outlet at 37 mm. Outlet widths were also chosen to reflect expected flow proportions, with the buffer outlet widest (2.20 mm), followed by the large particle (1.50 mm) and small particle (0.60 mm) outlets. These dimensions collectively ensure that laminar flow is preserved, streamlines remain stable, and particles follow their predicted trajectories based on size, resulting in accurate and continuous sorting.

# Design Features To Ensure Consistent Flow Rate 

To prevent disruptions to the streamlines and maintain proper separation, I focused on balancing the hydraulic resistance across all outlet channels. Because each outlet was designed to carry a different portion of the total flow, their channel widths and lengths were adjusted proportionally to achieve similar pressure drops at the outlet junctions. The buffer outlet, which carries the greatest flow, was set to 2.20 mm in width and 18 mm in length. The large particle outlet was made narrower (1.50 mm) but longer (26.4 mm) to increase its resistance, while the small particle outlet was narrowest (0.60 mm) and longest (66.6 mm) to further restrict flow and balance against the buffer channel.

Since the longer outlet channels exceeded the available footprint of the device, I used serpentine paths to fit the required lengths while maintaining the intended hydraulic resistance. The serpentine channels were designed with smooth, filleted corners to preserve laminar flow and prevent the formation of vortices or dead zones that could disrupt sorting. Outlet boundaries were defined using the midpoints between outlet centers to ensure consistent streamline capture for each particle size fraction. Throughout the design process, I adjusted the spacing and routing of the serpentine channels through iterative refinement to prevent overlap and ensure that all channels remained well separated during resin printing. This combination of geometric tuning and controlled resistance produced a balanced flow distribution across all outlets, preserving the clean laminar separation that is critical to effective PFF operation.

---

# Off-The-Shelf Parts

| Component                                                                 | Quantity |
|---------------------------------------------------------------------------|----------|
| Form 3 SLA Printer | 1 |
| Autodesk Fusion 360 | 1 |
| PDMS (Sylgard 184, 10:1 ratio) | 1 |
| Plasma Cleaner | 1 |
| Syringe Pumps | 2 |
| Polyethylene Microspheres (125-150 µm, 425–500 µm)| 1 |
| IPA (Isopropyl Alcohol) | 1 |
| Compressed Air System | 1 |

---

# 3D Printed Parts

| 3D Printed Part        | Purpose / Function |
|-------------------------|--------------------|
| uFluidic Device v1    | Initial interation |
| uFluidic Device v2+ | Refined design with adjusted dimensions |

---

# CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811eef13a8384cedcec?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

---

# Instructions 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Briefly list the most important steps for creating a ufluidic device with resin printing 
</p>

* **Design the Microfluidic Geometry (CAD):** Create the channel layout in CAD software. Include inlet/outlet ports, bonding buffer margins, and any alignment features. Ensure minimum channel widths and wall thicknesses match printer resolution and resin manufacturer’s recommendations. 
* **Export and Slice the Model:** Orient the device so that channels face upward to prevent resin pooling and print artifacts. Ensure the device is completely flush against the print bed. 
* **Print the mold:** Use a resin printer to print the negative mold. 
* **Post-Processing:** After printing, rinse the part in isopropyl alcohol to remove uncured resin. Use compressed air to remove debris. Then preform a 60 second surface-cure under UV light.
* **PDMS Casting and Curing:** Mix PDMS base and curing agent, pour into resin printed mold, and cure. Once cured, remove the PDMS layer. 
* **Bonding:** Clean PDMS layer and slide using Kim wipes and bond together. 
* **Final Testing:** Performa test of the device. 

---

# Discussion 

# Resin Printing Compared to Other Manufacturing Techniques 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Why resin printing compared to other manufacturing techniques? 
</p>

Resin 3D printing was chosen because it provides high precision, smooth surface finishes, and design flexibility required for microfluidic device creation. Resin printing can reliably produce complex 3D channel geometries like the serpentine outlet paths and variable-width sections directly from a CAD model. Modern SLA printers offer micrometer-scale resolution and great feature reproducibility, which are important for accurately defining the narrow-pinched regions and outlet channels in a PFF device. Resin printing creates durable and reusable products that are ideal for molds with PDMS casting.  

# How Design Could Be Scaled Up or Modified 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
How could your design be scaled up or modified to handle a wider range of particle sizes? 
</p>


My design could be scaled up by adjusting the pinched-section geometry. The pinched width should scale with the largest particle desired to pass through. For a larger size range, increase pinched width accordingly and re-calculate outlet streamlines. The three outlets could also be replaced with multiple, narrower collection outlets so there are more size bins. Tunning channel height can also act as extra control over resistance. 

# Factors That Set The Lower Limit On The Particle Size That Can Be Separated 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
What factors set the lower limit on the particle size that can be separated with pinch-flow fractionation? 
</p>

* **Pinched Channel Dimensions:** The pinched region must be narrow enough that particle size affects streamline positions. 
* **Surface Roughness and Dimensional Tolerance:** These are set by the printing and molding process and if these factors are comparable to particle diameter, flow becomes irregular and unpredictable, destroying the precise laminar flow necessary for PFF. 

--- 

# Why Are Resin-Printed Molds Coated with Parylene Prior to Casting PDMS? 

Parylene coating prevents the inhibition of PDMS curing caused by residual photopolymer resin components that can leach from uncoated prints. The parylene layer forms a smooth, chemically inert barrier that ensures clean demolding, smooth surface finish, and strong bonding between the PDMS and glass slide. Without coating, PDMS may remain tacky, tear on removal, or fail to cure fully—leading to leaks and poor optical clarity during testing.

--- 

# Hypothetical Applications 

Pinch flow fractionation is useful in a wide range of biomedical and materials applications, including:
* **Cell sorting** for diagnostics or single-cell analysis
* **Microbead purification** for chemical assays or encapsulated drug delivery
* **Environmental testing** where suspended particles must be classified by size
* **Additive manufacturing feedstock preparation** where consistent particle sizing improves powder flow 

---

# Features

* **Size-Based Particle Sorting:** The device uses a pinched microchannel region to align particles based on size before redistributing them into separate outlet streams through controlled laminar flow.
* **PDMS-on-Glass Construction:** The microchannels are cast in PDMS from a resin-printed mold and bonded to glass via plasma treatment, ensuring optical clarity and reliable sealing.
* **High-Resolution Fabrication:** SLA resin printing enables microchannel features down to 85 µm, maintaining smooth surfaces critical for laminar flow and accurate sorting.
* **Three-Outlet Flow Design:** Integrated flow resistance adjustments balance outlet pressures, preventing backflow and ensuring accurate particle separation.

---

# From Mold to Final Device
1. **CAD Modeling**  
   - Utilize Autodesk Fusion 360 to design the microfluidic geometry while following dimensional constraints
   - Begin with the provided base model (50 mm x 75 mm) to ensure the final PDMS device fits flush on the micrscope slide 
   - Fully constrain all sketches, clearly label features, and keep the design timeline minimal

2. **Resin Printing:** Print the mold using a Form 3 SLA printer
   - In PreForm, select a layer thickness appropriate to your feature resolution (25–50 µm recommended)
   - Position the mold so that the bottom face (the one that will contact the glass slide) is perfectly parallel to the resin vat to prevent visible layer lines
   - Ignore "cupping" warnings for flat parts 
   - Use black or high-temp resin for optimal dimensional accuracy and surface finish 
   - Start the print on an SLA printer and allow it to fully complete before removing from the build platform 

3. **Post-Processing**  
   - Wash the printed mold for 5 minutes on the build plate in the large FormWash
   - Remove it from the bed and wash for another 5 minutes in the smaller FormWash 
     - Do not exceed 15 minutes total of IPA exposure to prevent resin absorption
   - Lean the mold upside down to dry for at least 30 minutes 
     - Ensure no IPA pools inside the channels
     - The interior should appear evenly matte; glossy areas indicate uncured resin 
   - Do not touch the interior of the mold
     - Fingerprints or paper contact will increase surface roughness and transfer to the PDMS, likely causing sealing issues
   - Blow compressed air gently through the channels to remove any foreign particles/resin 
   - Perform a 60-second UV surface cure with supports still attached
     - Avoid extended curing or high heat, which can warp the part 
   - Carefully remove supports once cured, again avoiding contact with internal features 

4. **PDMS Casting**  
   - Mix SYLGARD™ 184 Silicone Elastomer at a 10:1 base-to-curing agent ratio by weight
   - Stir gently to minimize air bubbles and/or degas the mixture in a vacuum desiccator until no visible bubbles remain 
   - Pour the PDMS over the mold, ensuring even coverage across all features
   - Cure using one of the following options: 
     - 24 hours at 23 °C
     - 4 hours at 65 °C
     - 1 hour at 100 °C
     - 15 minutes at 150 °C (only if resin allows)
     - Recommended: 55 °C overnight for a complete cure without warping.
   - Allow the PDMS to cool before carefully peeling it off the mold 

5. **Plasma Bonding**  
   - Use Kim wipes only when handling PDMS devices 
     - Do not use PEC pads, as they leave fibers on the PDMS and glass surfaces 
   - Align and press the PDMS onto the glass slides 
     - Do not apply excessive pressure to shallow channels (<0.2 mm), which may collapse

6. **Device Preparation**  
   - Prepare particle suspensions of polyethylene (PE) beads in a 3% Tween solution to prevent bead sticking.
   - Use neutrally buoyant polyethylene microspheres (125–150 µm and 425–500 µm) to prevent floating or settling 
     - Water at 20–25 °C has a density of 0.9980 g/cc
     - Even smaller deviations will cause beads to float or settle 
   - Connect the PDMS device to syringe pumps using compatible barbed fittings.
   - Set flow rates to:
     - 3.0 mL/min for the buffer stream
     - 0.6 mL/min for the particle stream
   - Pressurize both inlets and outlets before starting to dislodge any trapped air bubbles.
   - Observe the separation of particle streams under a microscope.
   - Adjust flow rates if necessary to refine the pinch position or improve separation.

---

# How to Operate the uFluidic Device 
1. **Prepare Fluids**  
   - Load particle suspension and buffer solution into separate syringes.

2. **Connect Tubing**  
   - Attach inlets and outlets to the PDMS chip using barbed fittings.

3. **Set Flow Rates**  
   - Adjust syringe pumps to deliver precise flow ratios for effective pinch formation.

4. **Observe Separation**  
   - Use a microscope or camera to visualize particle trajectories through the outlets. 

---

{% include gallery caption="uFluidic Device Project Gallery" %}
