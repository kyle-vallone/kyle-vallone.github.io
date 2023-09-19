---
title: "Adjustable Handlebar-Mounted Phone Holder"
excerpt: "A flexible phone holder for your bike that can accommodate horizontal and vertical orientations."
header:
  image: /assets/img/bph_front_hori.png
  teaser: /assets/img/bph_real_banner.jpg
gallery:
  - image_path: assets/img/bph_front_hori.png
  - image_path: assets/img/bph_front_vert.png
  - image_path: assets/img/bph_back_hori.png
  - image_path: assets/img/bph_real_vert_use.jpg
  - image_path: assets/img/bph_rotation.gif
  - image_path: assets/img/bph_real_horz_use.jpg
  - image_path: assets/img/bph_real_vert_front.jpg
  - image_path: assets/img/bph_parts.jpg
  - image_path: assets/img/bph_real_vert_back.jpg
   
---

## Project Overview

## Key Features
* **Adjustable Fit:** The clamping action of the phone holder’s attachment mechanism allows it to fit handlebars ranging from 23 to 26 mm in diameter. Printed parts joined by a pair of screws clamp around the handlebars, using tension to ensure a secure fit; this avoids the need for set screws, which can damage surfaces.
* **Flexible Design:** The elastic TPU that makes up the “ball” of the ball-and-socket joint allows you to easily swap between vertical and horizontal display orientations. Thanks to the four resting positions of the mount, you can even face your screen away from you to avoid distractions while riding!
* **Quick Swap Functionality:** The flexible case attached to the mount allows you to quickly swap your phone from its normal housing to the holder in mere seconds. This works perfectly if you’re already using my MagSafe-equipped 3D printed phone case design, as it’s the same fit.
* **Durability:** Made from UV-resistant and durable ABS and TPU, this mount is built to stand the test of time, all the while protecting your phone on the way.

## CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6e11c1d8915bb95bfe?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

## Design Philosophy 
#### Top-Down Modeling
Top-down modeling was leveraged to create the bulk of this design. This approach features designs being created within the context of an existing assembly, rather than having separate parts be created individually and then joined together. By using in-assembly references, top-down design allows assemblies to be more readily configurable. Key elements of this approach specific to this project are described below.
* To ensure proper fit and continuity of the adjustable handlebar clearance hole, the two clamping components were based on the same initial profile sketch in a subassembly.
* Prototypes revealed that the diameter of the ball, which is printed in elastic TPU, should directly match the socket hole’s diameter. As such, the ball joint’s design directly projects this diameter from the profile sketch of the socket to allow easy adjustments. Because the TPU can accommodate compressive forces, this exact match reduces the play in the joint to confer stability to the mount.
* While part of the adapter was designed from a top-down approach to ensure proper fit and alignment with the arm’s mounting hole, the phone case was inserted from a previously developed design. This design leverages parametric design to enable quick customization to different phone models, but end users can also directly modify the CAD to insert a case design of their choosing. Breaking from the top-down approach allows for easy integration on this front, as the adapter component will remain the same while the phone case can be joined on top.

#### Design Rationale
* **Protection:** By fully enclosing the phone in a case incorporated into the design, the phone will be protected from unintended collisions without having to worry about it flying out of the clamp in the case of an especially rough jolt.
* **Ease of Adjustment:** The ball-and-socket joint that this mount relies on allows for quick switching between horizontal and vertical orientations, an essential feature for on-the-go applications. Simply twist the phone case, and the elasticity of the TPU allows the arm to conform to the new configuration in under a second. The time savings of this system are readily apparent when compared to other models that rely upon printed threads to manually swap between the orientations each time.
* **Additional Use Cases:** The four different resting positions incorporated into the socket end of the joint also allow this design to be suitable for any type of pipe-like rig. For instance, the mount could be attached to a curtain or towel rod for convenient, hands-free viewing around the house.
* **Material Choices:** This design uses multiple materials (ABS and TPU) to confer unique properties to different portions of the mount. Both polymers are quite durable and resistant to UV degradation, making them ideal for outdoor applications.
  * The clamping structure, including the socket end of the joint, is made of rigid ABS to allow secure mating to the handlebars and retainment of the ball joint. 
  * The ball joint and arm piece is made of elastic 95A TPU, which is fairly rigid compared to lower durometer filaments. However, the TPU confers enough flexibility for the ball and arm to compress below their respective “retaining nubs” on the socket end and for the arm to freely twist within the confines of its resting position to change orientation.
  * The phone case adapter component is also made of 95A TPU to facilitate easy insertion and removal of the phone from the mount. Additionally, the elasticity of the case makes it relatively resistant to any impacts that may be encountered on a bumpy ride.

## Assembly Instructions
1. Add M5 heat-set threaded inserts to the holes on the non-socket side of the top clamp part.
2. Press the ball end of the arm piece into the socket end of the top clamp part.
3. Fit the phone case adapter piece over the end of the arm. Line up the holes on each part and secure them together with a M5 x 20 mm bolt and M5 nut.
4. Fit the top and bottom clamp parts over your handlebars. Slot M5 x 10 mm socket head bolts into the holes on the bottom part of the clamp. Use a hex key to screw both bolts through the heat set inserts on the other side of the clamp until the mount fits snuggly on the handlebars.
5. Slide your phone into the phone case on the mount and adjust the arm to the desired orientation (vertical or horizontal). Rest the arm in one of the slots on the socket end below the retaining nubs to ensure the phone is secure within the mount. Happy riding!

## Bill of Materials
#### Off-the-Shelf Parts

| Item | Quantity |
| --- | --- |
| M5 Threaded Heat-Set Inserts | 2 |
| M5 x 10 mm Socket Head Bolt| 2 |
| M5 x 20 mm Socket Head Bolt | 1 |

#### 3D Printed Parts

| Item | Material | Quantity |
| --- | --- | --- |
| Clamp Bottom | ABS | 1 |
| Clamp Top (Socket End) | ABS | 1 |
| Ball Joint Arm | TPU | 1 |
| Phone Case Adapter | TPU | 1 |

## Photo Gallery

{% include gallery caption="" %}
