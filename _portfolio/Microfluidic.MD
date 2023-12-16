---
title: "Microfluidic Mixer"
excerpt: "VPP printing a mold to make a mixer for small amounts of fluid."
header:
  image: /assets/img/micro_real_top.jpg
  teaser: /assets/img/micro_render.png
gallery:
  - image_path: assets/img/micro_mold.jpg
  - image_path: assets/img/micro_casted.jpg
  - image_path: assets/img/micro_real_wood.jpg
  - image_path: assets/img/micro_real_top.jpg
  - image_path: assets/img/micro_setup.jpg
  - image_path: assets/img/micro_render.png
  - image_path: assets/img/micro_close.png
  - image_path: assets/img/micro_wash_top.jpg
  - image_path: assets/img/micro_wash_bottom.jpg



   
---

## Project Overview
Microfluidic devices allow us to manipulate small amounts of fluid, which provides the opportunity to limit solution use, therefore increasing workflow efficiency. Whether their use translates to requiring lower sample volumes in medical applications or saving on reagent/ingredient costs in industrial and research applications to reduce waste, microfluidics are becoming increasingly common as our society embraces nanoscale levels of innovation. However, when dealing with microscale volumes, a lack of turbulent flow can become an issue, as it limits mixing between different fluids. For that reason, microfluidic systems often require mixing elements to disrupt laminar flow, allowing fluids to mix into a homogenous solution before they are passed along to other devices.

Our device combines five types of passive microfluidic mixers to maximize mixing efficiency, while also allowing up to three inputs. One port is isolated further downstream from the other two, which allows it to be used as a secondary output to assess mixing success or allow an additional fluid to be inserted midway through the mixing path, after two other reagents have been sufficiently mixed. This could be used in medical applications to allow a sample to be introduced into an activated reagent mixture, for instance.

Microfluidic mold creation requires
* relatively high resolution for the creation of microchannels and 
* smooth surfaces on the printed models for successful casting. However, vat photopolymerization (VPP) was used to produce the microfluidic mold. 

For those reasons, several common additive manufacturing methods are not suitable for fabricating microfluidic molds, including FFF, SLS, and droplet printing. Instead, vat photopolymerization (VPP) was chosen to produce the mold in this project, as it can produce high-resolution models with relatively smooth surfaces while being fairly economical. However, one downside of VPP is the postprocessing required to appropriately wash and cure the mold. If the surface is not completely clean, it can either interfere with the parylene coating or PDMS casting, rendering the mold difficult to remove. Therefore, this technique is best used for molds being used for prototyping or specific research purposes that are not readily commercializable.

## Device Testing

<iframe width="315" height="560"
src="https://www.youtube.com/embed/Ds-Ahh6Uwkg?si=x9-xKWnGgD8_22XM"
title="YouTube video player"
frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
allowfullscreen></iframe>

## Design Philosophy 
#### Design Constraints
The minimum spot size of the VPP printer in this project, a Formlabs Form 3, is limited by its laser spot size, which is 85 μm. The minimum resolution, however, is 25 μm, which can allow different microchannels to be efficiently sized device. Our device in question was designed to fit flush on a 25 mm by 75 mm microscope slide, which gave plenty of room for us to experiment with multiple mixing methods. 

A final constraint to consider was the fact that these channels were small and thin features that could be prone to breakage during postprocessing of the mold or demolding of the device. As such, the aspect ratio of individual features needed to be below 3:1 to minimize the risk of unintended damage to the mold.

#### Design Rationale
This microfluidic used five types of passive mixers (adapted from designs reported in [this review of microfluidic devices](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3116190/)) to promote effective mixing by causing collisions between the flowing liquids to disrupt laminar flow. The mixer types are listed in the order they are implemented in the device.
* Y-intersection: Two input channels meet at a 45° angle, causing initial mixing.
* Serpentine mixer: Reminiscent of a path in the game "Snake," the fluid follows short paths punctuated by frequent 90° turns, in turn leading to frequent collisions with channel walls to promote mixing. This mixing technique was alternated with the inclined mixer between subsequent paths along the device's width, providing tight packing of mixing elements.
* Inclined mixer: This 3D geometry restricts the fluid path in the vertical and horizontal dimensions due to the triangular obstacles created by the alternating wedge design. As a result, fluids are forced to mix as the wedge-shaped cavities direct them to sway from side to side as they travel through the partially blocked channels.
* Zigzag mixers: Sharp 60° turns between short paths promote collisions with the channel walls, creating turbulent flow.
* Intersecting channels: In this mixing model inspired by countercurrent oxygen exchange in fish, connected vertical channels comprise the main path fluid takes, but less-well mixed fluid can also travel through smaller horizontal channels that intersect with subsequent fluid streams. Surface tension keeps fluid constrained in the horizontal channels until fluid flow displaces air in the adjacent vertical channels.

We chose to optimize the device for mixing small volumes, which would be ideal for applications in diagnostic medicine or laboaratory use to minimize reagent and sample consumption. This choice led us to start with channel heights of 600 μm, a main channel width of 300 μm, and a intersecting channel width of 100 μm. However, after these channels were damaged during postprocessing of our initial mold (specifically scraping off uncured regions that would disrupt the parylene coating), we increased the widths to 750 and 500 μm, respectively, and changed the height to 800 μm. This allowed us to meet project testing deadlines and assess mixing efficiency, though the size of the channels could be further optimized with additional prototyping.

## CAD Model

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6ee81113fbbbeb1d45?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

## Fabrication Instructions
1. **Preparation:** Export your model as a .STL and import it to your slicer (e.g. PreForm). If they occur, any cupping warnings can be ignored as long as the mold is printed flat on its base with a raft underneath. Export the sliced filde to your VPP printer.
2. **Washing:** With the model still on the build plate, wash it 2-3 times with isopropyl alcohol in a wash station. Then, manually wash the surface of the mold with isopropyl alcohol, making sure to clean off any remaining uncured resin. Ensure you wear appropriate PPE (gloves, lab coat, safety goggles) throughout this step!
3. **Curing:** Remove the model from the build plate, but do not remove supports yet. Cure the print in a cure station under UV light for 30 minutes at 60°C. 
4. **Support Removal:** Remove supports from the cured model. Ensure to wear protective eyewear to avoid being injured by any flying pieces.
5. **Additional Postprocessing:** This is an optional step to ensure leaching photoinitators will not affect the PDMS casting. Based on [this study](https://doi.org/10.1021/acs.analchem.0c04944) and our own experience, VPP prints can benefit from thermal and additional UV treatments to eliminate remaining photoinitiators that could interfere with this step. Both conditions can occur in tandem at either 60°C or 120°C.
6. **Parylene Coating:** Apply a parylene-C coating to the cured and postprocessed mold (we used Labcoter PDS 2010 parylene deposition machine). This coating aids in demolding and also allows for the creation of biocompatible devices.
7. **PDMS Casting:** Mix a 10:1 mixture of polydimethyl siloxane (PDMS) elastomer and curing agent by weight and pour into the mold. In a vacuum chamber, degass the mixture for 30 minutes. Them, cure the mixture for 80°C for 3 hours.
8. **Demolding and Plasma Bonding:** Remove the PDMS device from the mold. Plasma treat the device (we used a PlasmaFlo PDC-FMH plasma cleaner) and bond it to a 75 mm by 25 mm glass microscope slide to create a leak-proof seal.

## Media Gallery

{% include gallery caption="" %}
