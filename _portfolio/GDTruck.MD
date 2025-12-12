---
title: "Generative Design Truck"
excerpt: "A lightweight, generatively-designed truck hanger featuring an integrated motor mount optimized for both Nylon 12 and ALSi10Mg SLS fabrication."
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

Insert Response Here

___

# Comparison between the Nylon and Aluminum Outcome
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
A comparison between the nylon and aluminum outcome. 
</p>

Insert Response Here

---

# Critique on Generative Design 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Critique generative design. How useful is it really? What are the drawbacks? What applications would generative design be most useful in?
</p>

Insert Response Here

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

<div class="gallery">
  <img src="assets/img/5%20BikeMount-1.JPG" />
  <img src="assets/img/5%20BikeMount-2.JPG" />
  <img src="assets/img/5%20BikeMount-3.JPG" />
  <img src="assets/img/5%20BikeMount-4.JPG" />
  <img src="assets/img/5%20BikeMount-5.JPG" />
  <img src="assets/img/5%20BikeMount-6.JPG" />
  <img src="assets/img/5%20BikeMount-7.JPG" />
  <img src="assets/img/5%20BikeMount-8.JPG" />
</div>

<style>
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 10px;
}
.gallery img {
  width: 100%;
  border-radius: 6px;
}
</style>

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
| SLS 3D Printer (Fuse 1 for Nylon 12 / Metal Vendor for ALSi10Mg) | 1 |
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
