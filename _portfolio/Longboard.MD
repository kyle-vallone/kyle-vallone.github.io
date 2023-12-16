---
title: "Generative Design Longboard"
excerpt: "Designing an electric longboard using generatively designed trucks and a large-format 3D-printed deck."
header:
  image: /assets/img/lb_real.jpg
  teaser: /assets/img/lb_render_motor.png
gallery:
  - image_path: assets/img/lb_render_alum.png
  - image_path: assets/img/lb_render_alum_motor.png
  - image_path: assets/img/lb_render_motor.png
  - image_path: assets/img/lb_render_nylon.png
  - image_path: assets/img/lb_scale_bottom.jpg
  - image_path: assets/img/lb_scale_alum.jpg
  - image_path: assets/img/lb_scale_nylon.jpg
  - image_path: assets/img/gd_front_1.jpg
  - image_path: assets/img/gd_back_1.jpg
  - image_path: assets/img/gd_side_1.jpg
  - image_path: assets/img/gd_truck_mounted
  - image_path: assets/img/lb_petg_proto.jpg
  - image_path: assets/img/lb_twist.gif
  - image_path: assets/img/lb_printing.jpg
  - image_path: assets/img/ridingboard.gif
  - 
   
---

## Project Overview
This project endeavored to use two different 3D printing technologies to create components for an electric longboard. 
* Selective laser sintering (SLS) was used to produce longboard trucks with an integrated motor mount for the longboard. To design these trucks, generative design was leveraged to generate outcomes that uniquely fit the loads and constraints specific to this use case while minimizing the mass of material produced. Due to the flexibility of the generative design workflow, outcomes were generated to fit two materials: Nylon 12 (printed on a Formlabs Fuse 1) and AlSi10Mg (an aluminum alloy).
* Large format fused filament fabrication (FFF) printing was used to create the longboard deck. As the printed longboard is heavier than conventionally manufactured decks, a ["short longboard" style](https://vandemlongboardshop.co.uk/collections/short-longboards) was chosen to minimize the weight and size of the overall assembly to make it easier to carry around for everyday use cases. This short longboard style also lends itself to an agile riding style due to the smaller turn radius of the wheelbase.

## CAD Models
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6e230000b4cd7d3166?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6e81cc7cfd7c2935f1?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6e1860f48bf4d04e0c?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>


## Design Discussion: Generative Design and Powder Bed Fusion

<img src="/assets/img/powder_print.gif" style="width:300px;"/> 

Powder bed fusion is perfect for pairing with generative design, as layers of unmelted powder serve as support for future layers allow for nearly unrestricted geometries to be printed. Recoating over the printed (and unprinted) regions after the desired regions of the build volume have been melted by the laser then provides a new layer of substrate for the laser to act upon. For most materials, this allows parts printed through powder bed fusion to not require any support. In these cases, all that needs to occur is a thorough cleaning of the parts to remove any unfused powder particles. However, in the case of metal powder printing, supports are often required (with extensive postprocessing to remove them) to avoid unsupported geometries sinking into the powder layers below, as the melted regions are denser than the unfused powder. For this reason, it made sense to design the trucks out of both nylon and aluminum to reflect a variety of manufacturing circumstances.

Another benefit of powder bed fusion is the ability to recycle the unused powder that does not end up as part of the model. Unlike the lengthy process of recycling support material from FFF printing, the leftover powder can easily be siphoned off and reincorporated into a new batch. However, due to the exposure to the high temperatures of the build volume, this powder needs to be "refreshed" by adding in virgin powder to balance out the degraded material properties of the recycled powder.

Generative design does have one significant drawback, namely the extensive CAD work that still must go into setting the constraints that the program will solve around. All obstacles that could be encountered by the truck need to be meticulously blocked out--from the obvious (wheels, pulleys, etc.) to the unexpected (rotational clearance to fit the part into position on its mounting plate). These obstacles are in addition to the preserved geometry that makes up the functional components of each part--in the truck's case, this was the motor mount geometry, the "sheath" that holds the axle, and the pivot joint and kingpin geometries. Overall, blocking out all of the obstacles can often take up more time than it would take to CAD the part yourself. However, generative design allows the same constraints and loads to be applied to multiple materials, allowing further iterations to be quick and easy. Since the load simulation work is already built into the workflow, it can simplify the process of designing and testing. However, the use of a FFF printed prototype is not to be understated, as can be seen in the media gallery. These prototypes revealed many unforseen obstacles that needed to be blocked out in future iterations, which saved money that would have been wasted on insufficient SLS printed designs.

Generative design is promising as we enter the next AI-driven industrial revolution. Optimizing geometries to minimize mass, when paired with suitable production methods, has the potential to save thousands of dollars on production by minimizing wasted material. Both the automotive and aerospace intustries stand to benefit from these types of design optimizations, as they rely on specialized parts with unique geometries already. Autodesk, the creator of Fusion 360, has already [partnered with General Motors](https://www.autodesk.com/customer-stories/general-motors-generative-design) and Honda to explore generative design in the automotive industry, working with them to develop lightened designs for seat belt latches, brake calipers, and crankshafts. Many of these designs are reminiscent of how the AI generated connections between the body of the longboard truck and the motor mount--clearly optimized to take stress in the directions experienced in the use case. Even beyond transportation, Jacobs has been employing generative design with Autodesk competitor PTC (the maker of OnShape) to [optimize designs for space suits that will be used by NASA](https://www.ptc.com/en/case-studies/jacobs-engineering-generative-design-aerospace), achieving significant weight savings (50%) that will make it easier for astronauts to move and live in these suits while also saving on fuel costs to send this vital exploration equipment to the stars. As generative design becomes increasingly integrated with manufacturing, the future is bright to produce parts that are specialized, safe, and more environmentally friendly as we seek to minimize waste and maximize innovation.

## Design Philosophy: Large-Format 3D-Printed Longboard Deck
The longboard design was a much simpler process than generative design, both due to the deck being a simpler design and the fact that it required fewer load cases. It was optimized to support the weight of a 200 lb rider with no more than 12 mm of deflection in the vertical plane. The ["short longboard" style](https://vandemlongboardshop.co.uk/collections/short-longboards) was chosen both to minimize weight for ease of everyday use when carrying it inside buildings to store it, which also led to an agile riding style being promoted. 

This chosen "short" style, with a 25 in wheelbase, had the added benefit of minimizing the displacement of the board, as the weight of the rider would be better supported by the trucks being closer together. When it came time to simulate the load of the rider's weight on the board, which had the thickness conservatively set at 15 mm, the deflection turned out to be well below the minimum--the maximum deflection was only 2.44 mm. This gave the board a minimum safety factor of 7.41, well above the standard 2.0.

<img src="/assets/img/lb_sim.png" style="width:600px;"/> 

To minimize compressive forces on the board from fasteners securing the trucks, machined aluminum blocks were instead used to secure the truck assemblies to the board. As such, pockets with a lip were integrated into the board to allow for secure mounting of these blocks; the wheelbase was set relative to the center of these blocks in the design.

Lastly, the board's aesthetic design was optimized for simplicity, with a simple "arrow" tip on both ends. The overhangs on the arrows were minimized (<45°) to allow the board to be printed along its thin edge, which make the layer lines of the print create the texture of the deck. A celebration of how far 3D printing has come, this deck would be the perfect gift for the 3D printing enthusiast!

Scale models of the longboard assembly were printed using normal-scale FFF printers, allowing the designs to be assessed before they went into production. These images can be seen in the media gallery.

## Media Gallery

{% include gallery caption="" %}
