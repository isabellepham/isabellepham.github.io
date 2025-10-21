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

# How to Operate the Syringe Pump 
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
