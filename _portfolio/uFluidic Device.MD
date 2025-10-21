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

# What is Pinch Flow Fractionation? How does it work? 

Pinch Flow Fractionation (PFF) is a microfluidic techinque used to separate particles or cells based on size within a continous laminar flow. It works by combining two fluid streams inside a microchannel. One stream carries the particles suspended in fluid while the other is a pinched flow that narrows the particle stream as both enter a constricted "pinch" region. 

Inside this narrow section, all particles are forced toward one side wall of the channel and align along streamlines determined by their size. When the channel widens again, the streamlines separate. Larger particles, which experience more lateral displacement due to their size, move toward the center, while smaller particles stay closer to the wall.

By collecting fluid from different outlet channels, particles of different sizes can be continuously separated without filters or external forces.

# Application of PFF for sorting small particles 

One important application of pinch flow fractionation (PFF) is in biomedical diagnostics for isolating circulating tumor cells (CTCs) from whole blood. CTCs are rare cancer-derived cells in the bloodstream whose detection can provide early indication of metastasis or treatment response. Because CTCs are typically larger and stiffer than most white blood cells, PFF can exploit this size (and deformability) difference to separate CTCs under continuous laminar flow conditions. For example, Pødenphant et al. used PFF to separate LS174T cancer cells from white blood cells with efficiencies above 90% for both cell types. ([Pødenphant M. et al., *Lab on a Chip*, 2015, 15, 4598-4606](https://pubs.rsc.org/en/content/articlelanding/2015/lc/c5lc01014d))

There are several key benefits of PFF over traditional filtration or sieve-based separation techniques:

* **Reduced clogging and fouling**: Traditional filters rely on fixed pore sizes, which can become clogged by debris or large aggregates, whereas PFF uses hydrodynamic alignment of particles in a sheath/pinch flow and separation via streamlines, reducing clogging risk.
* **Gentle, label-free processing**: PFF does not require affinity tags or external forces (e.g., electric, magnetic) and exerts lower shear stress on particles/cells compared to many mechanical or active separation methods, preserving viability and functionality of cells.
* **Continuous and tunable separation**: Because PFF works in a continuous flow channel, assessments of flow-rate ratio and channel geometry enable control of the cutoff size (critical diameter) for separation. For instance, Pødenphant et al. tuned the critical diameter by adjusting drain pressure in the PFF device.
* **Better suitability for overlapping size distributions**: In their study, Pødenphant et al. found that even when cancer cells and WBCs had overlapping size distributions, they achieved high separation efficiency by exploiting deformability differences in the hydrodynamic alignment process.

In summary, for applications requiring sorting of small particles or cells — especially delicate biological particles like CTCs — PFF offers an elegant, efficient, and low-stress alternative to conventional filtering techniques, with demonstrated capability in high-efficiency cell separation.

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

# From Mold to Final Device
1. **CAD Modeling**  
   - Utilize Autodesk Fusion 360 to design the microfluidic geometry while following dimensional constraints
   - Begin with the provided base model (50 mm x 75 mm) to ensure the final PDMS device fits flush on the micrscope slide 
   - Fully constrain all sketches, clearly label features, and keep the design timeline minimal
   - 

2. **Resin Printing: ** Print the mold using a Form 3 SLA printer
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
