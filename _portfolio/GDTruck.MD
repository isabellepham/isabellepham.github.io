---
title: "Generative Design Truck"
excerpt: "A lightweight, generatively-designed truck hanger optimized for both Nylon 12 and ALSi10Mg SLS fabrication."
header:
  image: /assets/img/6 GDTruck-Banner.JPG
  teaser: /assets/img/6 GDTruck-Banner.JPG
gallery:
  - image_path: assets/img/5 BikeMount-1.JPG
  - image_path: assets/img/5 BikeMount-2.JPG
  - image_path: assets/img/5 BikeMount-3.JPG
  - image_path: assets/img/5 BikeMount-4.JPG
  - image_path: assets/img/5 BikeMount-5.JPG
  - image_path: assets/img/5 BikeMount-6.JPG
  - image_path: assets/img/5 BikeMount-7.JPG
  - image_path: assets/img/5 BikeMount-8.JPG
  - image_path: assets/img/5 BikeMount-8.JPG
  
---

I designed a generative longboard truck hanger with an integrated motor mount using Fusion 360. The model was built from essential preserved interfaces—kingpin seat, axle bore, bearing contact points, belt envelope, and motor mounting slots—to give the generative solver freedom to minimize mass while meeting all mechanical and spatial constraints.

Two outcomes were produced for Nylon 12 and ALSi10Mg, allowing comparison of how material stiffness and manufacturing constraints influence the resulting topology. After minor refinements for printability, the ALSi10Mg design was fabricated using SLS powder-bed fusion and assembled onto the full longboard to validate axle alignment, belt tensioning, wheel clearance, and motor ground clearance.

---
# Pairing of Powder Bed Fusion and Generative Design 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
The unique pairing of powder bed fusion and generative design and their applications in either aerospace or automotive industries. Please research a specific commercial example (not on the slides), where generative design has been used to reduce the number of components in an assembly. 
</p>

Insert Response Here

---

# Importance of Applying Proper Load Cases
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
The importance of applying the proper load cases and how to improve this process. How did you determine which forces to apply to the model? Where did you place the structural constraint and how will this placement affect the outcome?
</p>

| #  | Load Case Name                      | Type                    | Magnitude             | How Computed / Split               | Direction & Application Point           | Notes                                        |
| -- | ----------------------------------- | ----------------------- | --------------------- | ---------------------------------- | --------------------------------------- | -------------------------------------------- |
| 1  | Rider static load (conservative)    | Point force             | **735.75 N upward**   | 75 kg × 9.81 = 735.75 N            | Upward at kingpin pivot                 | Baseline static load                         |
| 2  | Rider shock/impact load             | Point force             | **1471.50 N upward**  | Static load × 2                    | Upward at pivot                         | Conservative shock scenario                  |
| 3  | User-applied pivot load (your run)  | Point force             | **1500 N upward**     | Given (rounded conservative value) | Upward at pivot                         | Used for main generative run                 |
| 4  | Bearing support vertical reactions  | Reaction forces         | **750 N upward each** | 1500 N / 2 supports                | Upward at each connecting-rod support   | Assumes symmetric geometry                   |
| 5  | Belt tangential load (total)        | Tangential force        | **558.5 N**           | Given                              | Tangential at pulley                    | Source of horizontal shear                   |
| 6  | Belt tangential (split to supports) | Tangential point forces | **279.25 N each**     | 558.5 / 2                          | Left: toward motor; Right: toward pivot | For shock: ×1.5 → 418.9 N, ×2 → 558.5 N each |
| 7  | Motor torque                        | Moment                  | **8000 N·mm**         | Given                              | Moment at motor shaft center            | Main torsional load                          |
| 8  | Motor weight moment                 | Moment                  | **312 N·mm**          | (0.86 × 9.81) × 37 mm              | Applied at motor CG                     | Small but included                           |
| 9  | Motor weight (vertical)             | Point force             | **8.44 N downward**   | 0.86 × 9.81                        | Downward at motor CG                    | Minor vertical load                          |
| 10 | Belt tension (axial)                | Tension force           | **558.5 N**           | Given                              | Acts along belt line                    | Contributes to axial loading                 |

I determined which forces to apply to this model largely with the help of conversing with Dr. Florian and utilizing tools like AI to assist in guiding my thinking. 

How I determined which forces to apply (and why)

1. **Start from system-level physics:** The rider weight is the primary global load. Using 75 kg × 9.81 gives the static gravity reaction (735.75 N). For safety, shock/impact multipliers (×1.5–×2) are standard to approximate dynamic loads from landing, bumps, or rough terrain. You chose 1,500 N as a convenient conservative shock value — that sits between ×2 of 735.75 (1,471.5 N) and a small round-up.

2. **Distribute loads by contact / support geometry:** If the pivot is the structural interface to the deck, apply the upward deck reaction at that pivot. If that pivot reaction distributes to two bearing/support points, split by symmetry (1,500 / 2 = 750 N per bearing). If geometry is asymmetric, use static equilibrium (moments about a point) to redistribute based on lever arms.

3. **Use component-specific forces for drivetrain loads:** Belt tension and belt tangential force are calculated from motor torque / pulley geometry or given. Those are applied as tangential point loads at the pulley/mount supports and cause shears on the connecting rods. Split the total tangential force between supports based on symmetry or lever arms.

4. **Include moments and small secondary loads:** Motor torque (8,000 N·mm) is an applied moment. Motor mass creates a small bending moment (≈312 N·mm) and a small vertical force (≈8.44 N). Even if small, include them because they change local stress states and interaction with belt/motor loads.

5. **Apply conservative dynamic factors where appropriate:** For shock or impact cases multiply forces by ×1.5–×2. Do sensitivity runs to understand which loads govern design.

___

# Comparison between the Nylon and Aluminum Outcome
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
A comparison between the nylon and aluminum outcome. 
</p>

The differences between the Nylon 12 and ALSi10Mg (aluminum) generative design outcomes were immediately noticeable. Across every simulation, the aluminum outcome consistently appeared more slender, efficient, and lightweight. This makes sense given aluminum’s higher stiffness and strength-to-weight ratio; the algorithm can rely on the material’s mechanical properties to carry loads without needing to add significant bulk. As a result, the aluminum design typically featured thinner struts, more open geometry, and fewer solid sections, all while still meeting the performance constraints.

In contrast, the Nylon 12 outcome was significantly more robust and bulky. Nylon is far more flexible and compliant than aluminum, so the generative design tool compensated by adding mass and thickening load-bearing regions. I also noticed that the nylon geometry was much more sensitive to changes in loading conditions. When I increased forces or added additional constraints, the nylon model grew disproportionately in size, as if the algorithm had to over-build the structure to maintain stiffness and prevent deformation. Meanwhile, the aluminum model responded to these same load increases in a different way: rather than simply adding more material, it tended to generate additional connection points and branching structures to redistribute stress efficiently. This led to designs that were still lightweight but strategically reinforced.

Overall, the comparison highlighted how strongly generative design depends on material behavior. Aluminum allowed for minimal, optimized geometries with refined load paths, whereas nylon required heavier, more conservative forms to achieve the same level of performance.

---

# Critique on Generative Design 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Critique generative design. How useful is it really? What are the drawbacks? What applications would generative design be most useful in?
</p>

Working with generative design for this project showed me both its strengths and its limitations. On the useful side, it was extremely effective at pursuing the performance goal we gave it: minimizing mass. Manually lightweighting the hanger would have required making cutouts, reprinting, stress-testing, and repeating that cycle many times. Generative design essentially automated that entire exploration. In fact, one of its biggest strengths is its ability to explore massive design spaces that humans cannot practically iterate through. While a person might test a handful of design variations, generative design can evaluate dozens or even thousands of possibilities simultaneously. This is especially valuable in situations where many constraints are interdependent, or where small performance improvements really matter—such as weight reduction, strength-to-mass optimization, or stiffness tuning.

I also found generative design useful for understanding how material choice affects geometry. The Nylon 12 and ALSi10Mg outcomes looked noticeably different, reflecting how the tool adapts its topology to specific material properties. This ability to compare multiple materials quickly is something traditional CAD workflows can’t do nearly as efficiently. More broadly, this is why generative design shines in early-stage ideation. It often generates shapes or configurations that a human designer might not think to try which sometimes leads to strange or organic-looking, but nonetheless structurally valid.

However, using the tool also made its limitations very clear. First, generative design is extremely dependent on the accuracy of the parameters and load cases you provide. The algorithm optimizes for exactly what you tell it to, nothing more. Since I don’t have extensive training in structural load modeling, the accuracy of my results was ultimately limited by the quality of my inputs. If the load cases are unrealistic or incomplete, generative design has no way to correct for that—it simply produces an “optimized” version of a flawed problem statement. This is a common critique: optimization is not the same as good design. Important qualitative factors such as ergonomics, manufacturability, ease of maintenance, and experiential considerations are not captured in the simulation at all. Generative design can easily give you “highly optimized garbage” if the problem is framed poorly.

Manufacturability is another major drawback. While many generative geometries look elegant in simulation, they can be extremely difficult or expensive to produce without advanced additive manufacturing. Even with 3D printing, the organic and lattice-like forms generated can be fragile, hard to post-process, or prone to failure if printed even slightly out of spec. When I attempted to print my generative design using FFF methods, I encountered numerous print errors and failures, and removing the support material was both time-consuming and messy. Additionally, setting up obstacles and “non-design spaces” in Fusion was surprisingly tedious. Unlike manual modeling—where you directly shape the geometry you want—generative design requires explicitly defining all the regions you don’t want included. For a component with many interface points and moving parts, like the longboard truck and motor mount, this setup introduces significant overhead and adds complexity to the workflow.

Generative design also has high computational and expertise demands. Generating studies take a while, and interpreting the outcomes requires engineering judgment. Some designs look promising but have stress concentrations hidden in unusual places. Others are technically valid but impractical to assemble or repair. This reinforces a key point: generative design is not a tool for novices; it’s a multiplier for knowledgeable engineers. Without that engineering context, outputs can be misleading.

Additionally, generative structures can behave unpredictably in edge cases. Their organic geometries rely heavily on exact load paths and precise material behavior. Small changes in real-world conditions—such as belt tension, surface imperfections, vibrations, or impact loads—can cause failures that the simulation never accounted for. For consumer-facing hardware where reliability and safety matter, this is a serious concern.

Despite these drawbacks, generative design has clear application areas where its advantages outweigh its limitations. It is especially compelling in aerospace and automotive engineering, where weight reduction translates directly into energy savings, performance improvement, and cost reduction. It also pairs naturally with additive manufacturing, which can produce complex, organic structures that would be impossible using traditional machining. Other strong domains include architecture, robotics, biomechanics, and industrial design—fields where complex load paths or nature-inspired forms can outperform conventional shapes.

---

# Generated Outcomes - Iterations before FFF Printing

<iframe width="560" height="315"
src="https://www.youtube.com/embed/8_hajX6IUJg"
frameborder="0"
allowfullscreen>
</iframe>

---

# CAD Model of ALSi10Mg outcome 

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811f02ce06be8df9cdb?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

---

# CAD Model of Nylon 12 outcome 

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b6028114112925b620b0995?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

---

# Rendering of ALSi10Mg Longboard Assembly

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811c29792b7a54f8751?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

---

# GD Truck Functioning 

<iframe width="560" height="315"
src="https://www.youtube.com/embed/_zGIuHbPmDc"
frameborder="0" allowfullscreen></iframe>

---

# ALSi10Mg Model 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Real life images of the ALSi10Mg model pSLS printed and attached to the longboard
deck.
</p>

---

# Features

* **Generative Lightweight Structural Geometry:** The final hanger integrates both the traditional hanger body and motor mount into a single consolidated component. The generative design engine minimized mass while maintaining stiffness sufficient to support rider weight, resist motor torque, and withstand the forces transmitted through the kingpin and axle.
* **Integrated Adjustable Motor Mounting System:** The preserved regions include slotted motor-mounting holes enabling ±4 mm of belt tension adjustment. Geometry around the motor region automatically forms efficient load paths, ensuring the motor plate remains rigid under acceleration while avoiding print-region violations of the Fuse 1 SLS build volume.
* **Optimized for Dual Materials:** Nylon 12 & ALSi10Mg - Two independent generative design studies were run. One on Nylon 12 and one on ALSi10Mg. Comparing both solutions informed how material stiffness influences topology, mass distribution, and manufacturability.

---

# Off-The-Shelf Parts

| Component                                                                 | Quantity |
|---------------------------------------------------------------------------|----------|
| [Paris V2 Mounting Plate and Kingpin (attached to skateboard)](https://www.loadedboards.com/products/paris-v2-180mm-50-trucks) | 1 |
| Bushings | 2| 
| Washers | 2 | 
| Kingpin Nut | 1| 
| [6374 Brushless Motor (63 mm x 55 mm)](https://www.amazon.com/Flipsky-Electric-Skateboard-Dustproof-Brushless/dp/B086YN7SSB) | 1 |
| [90 mm x 52 mm Longboard Wheels](amazon.com/gp/product/B091GGR3RM) | 2 |
| [Wheel Pulley Set](https://www.amazon.com/gp/product/B07JN246JW?th=1) | 1 | 
| SLS 3D Printer | 1 |
| [Calipers](amazon.com/Neiko-01407A-Electronic-Digital-Stainless/dp/B000GSLKIW?crid=1C7BPKT5NIPWY&keywords=calipers&qid=1644422896&sprefix=calipers,aps,73&sr=8-4&th=1&linkCode=sl1&tag=drd0cf-20&linkId=73d2c46816e51f3eafe02410811438e6&language=en_US&ref_=as_li_ss_tl) | 1| 
| Wrench | 1 |
| Screwdriver | 1 | 

---

# Generated Outcomes

| Generated Outcomes| Purpose / Function |
|------------------|--------------------|
| Generative-Designed Truck Hanger (Nylon 12) | Design generated to compare with Aluminum outcome, helpful in evaluating forces. |
| Generative-Designed Truck Hanger (ALSi10Mg) | Final metal component, powder printed to be used for physical longboard assembly testing |

---

{% include gallery caption="Multi Material Pliers Gallery" %}
