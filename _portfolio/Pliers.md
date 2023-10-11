---
title: "Multimaterial Pliers"
excerpt: "Pliers with rigid handles and jaws and an elastic hinge, perfect for gently gripping resistors."
header:
  image: /assets/img/pliers_render.png
  teaser: /assets/img/pliers_side_profile.jpg
gallery:
  - image_path: assets/img/pliers_side_profile.jpg
  - image_path: assets/img/pliers_iterations.jpg
  - image_path: assets/img/pliers_render.png
  - image_path: assets/img/pliers_section.png
  - image_path: assets/img/pliers_printing.gif
  - image_path: assets/img/pliers_flex.gif
  - image_path: assets/img/pliers_vert_move.gif
  - image_path: assets/img/pliers_horz_front_move.gif
  - image_path: assets/img/pliers_horz_side_move.gif

   
---

## Project Overview
## The Challenge
These pliers were designed with precision electronics in mind. They should able to securely, but gently, pick up and move small electrical components like through-hole resistors, shifting the burden of fine motion away from overworked fingers. Furthermore, this design should be able to be manufactured using a print-in-place method—coming off a 3D printer’s build plate fully assembled and ready to use!
## Key Features and Specifications
* **Adjustable Jaws:** The flexible hinge of this design allows the 20 mm long plier jaws to flex inward and outward. This allows for a maximum jaw capacity of 28 mm—much greater than the resting jaw capacity of 8 mm—while still enabling the pliers to pick up something as thin as a sheet of paper!
* **Elastic Hinge:** A 3x3 square lattice of flexible TPU material couples the actuation of the handles to that of the jaws in both directions. The elastic nature of the hinge prevents too much force from being applied to the delicate electrical components these pliers were designed to be compatible with.
* **Flexibility:** The central location of the elastic hinge allows the entire plier assembly to flex and operate with the jaws at up to a 90° angle from the handles—perfect for picking up parts in hard-to-reach corners.
* **Slim Profile:** Measuring only 7 mm thick, 115 mm long, and 80 mm wide, this tool can easily slide into your pocket to serve as the perfect workplace companion or toy.

## CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6e71791743469adeb0?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

## Design Philosophy 
#### Print-in-Place Parts
Print-in-place manufacturing allows 3D printers to produce functional, articulating mechanisms all in one go, with no assembly required. The applications of print-in-place models are many—for instance, they can be used to… 
* test 3D printer tolerances, like this [print-in-place combustion engine](https://www.printables.com/model/212989-print-in-place-engine-benchmark-the-bengine),
* produce toys, like this [articulating dragon](https://cults3d.com/en/3d-model/art/crystal-dragon-articulating-flexi-wiggle-pet-print-in-place-fantasy), which is extremely popular on online marketplaces, 
* start new fashion trends, like this [3D-printed chain mail](https://www.thingiverse.com/thing:3096598),
* create compliant mechanisms, such as these [designs from the BYU CMR Group](https://compliantmechanisms.byu.edu/maker-resources),
* make tools on-demand, like this [wrench made on the International Space Station](https://www.nasa.gov/missions/station/space-station-3-d-printer-builds-ratchet-wrench-to-complete-first-phase-of-operations/), or
* manufacture multimaterial parts with varying mechanical properties, like this [bearing block from Igus](https://toolbox.igus.com/motion-plastics-blog/multi-material-parts-from-3d-printer)
While incorporating materials with different mechanical properties can elevate the functionality of print-in-place designs, such as using both rigid and elastic materials, differing materials may not adhere well to each other. Therefore, when using both rigid and elastic parts in print-in-place modeling, care needs to be taken to appropriately retain the regions made from each material in the design. Creating mechanical mates, such as encapsulated or overlapping regions and/or dovetail joints, to force these materials to stay together, is therefore essential for designs like these. 
#### Design Rationale
* **Elastic Hinge:** This component uses a 3x3 square matrix of flexible 95A TPU. This flexible material allows the squares to compress into a diamond shape, which in turn compresses the matrix as a whole. Because the region can compress in both the X and Y directions, the jaws can both expand and contract depending on whether the handles are pulled apart or pushed together, respectively. The elastic deformation of the matrix allows the pliers to return to the resting position (in which the jaws are parallel) when no force is applied to the handles. 
* **Jaws:** The jaws are made of rigid and durable ABS. This allows them to firmly grip components, but due to the elastic hinge, they cannot apply a crushing force since the square matrix will deform before an object is crushed. This serves both to protect the fragile electronics the pliers were designed to handle while also allowing them to be used safely by young children without the danger of injury. Ridges along the inside faces of the jaws facilitate gripping cylindrical resistors, as the ridges are spaced so that the resistors can settle in between the gaps.
* **Handles:** The handles are also made of rigid ABS to facilitate smooth actuation. The handles were designed to have a lightening pattern to serve as a point of visual interest while also reducing material use to save money and time while printing.
* **Interface:** The interface between the flexible hinge and the rigid handles/jaws relies on a combination of **three dovetail joints** per section (12 in total) as well as **two encapsulated regions** per section (8 in total). The encapsulated regions are bounded by the two dovetail wedges and a strip of material that connects the three joints together, as seen below.
<img src="/assets/img/pliers_section.png " alt="A cross-section of the interface between the hinge and rigid components." style="width:300px;"/> 

## Print Settings
These pliers can either be printed in place using a dual extrusion printer, or the elastic hinge can first be printed separately before being inserted into its respective cavity mid-print when the rigid handles and jaws are printed. 
* If dual extrusion is used, printing with an **ooze shield** is recommended to avoid unintended filament deposition from the nozzle on standby.
* The latter method is beneficial because both parts can be **produced in under an hour** (on fast CoreXY machines) because multiple filament changes are not needed, but it does require the insertion of a pause G-code during the slicing process. 
  * The following settings were successfully used with this pause method on a **[Bambu Lab P1S](https://us.store.bambulab.com/products/p1s)** (which has vibration compensation, an enclosure, and a direct drive extruder) to achieve a sub-hour print time. The engineering of the P1S allows TPU, which was used for the hinge, to be printed much faster than on typical hobbyist printers.
  * **General Settings**
    * Speed: 200 mm/s (first layer: 50 mm/s)
    * Retraction: 0.8 mm at 30 mm/s
    * Layer Height: 0.28 mm
    * Z-Hop enabled to prevent accidental collisions with inserted hinge component
    * Pause at the beginning of layer 23 (Z = 6.36) using M400 to allow the hinge piece to be inserted (the pause machine code specific to these machines—this may be different for other vendors)
  * **Elastic Hinge**
    * Material: 95A TPU
    * Temperature: 240°C (nozzle) / 40°C (bed)
  * **Rigid Jaws and Handles**
    * Material: ABS
    * Temperature: 270°C (nozzle) / 90°C (bed)

## Media Gallery

{% include gallery caption="" %}
