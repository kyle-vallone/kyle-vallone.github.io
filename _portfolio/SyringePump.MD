---
title: "DIY Syringe Pump"
excerpt: "A DIY pump with a configurable flow rate able to accommodate syringes from 10 to 20 mL."
header:
  image: /assets/img/sp_real_assembly.png
  teaser: /assets/img/syringe_pump_render.jpg
gallery:
  - image_path: assets/img/sp_real_assembly.png
  - image_path: assets/img/sp_adaptive_jaws.png
  - image_path: assets/img/syringe_pump_render.jpg
  - image_path: assets/img/sp_wiring.png
   
---

# Project Overview
Syringe pumps are used in both healthcare and biomedical research settings to dispense precise amounts of liquid. By translating the rotational motion of a motor shaft to linear motion along a lead screw, syringe pumps can apply mechanical force to depress a loaded syringe in a controllable and tunable manner. This DIY syringe pump uses 3D printed parts and common off-the-shelf components to provide a low-resource, affordable alternative to commercial syringe pumps. Furthermore, the pump can be operated with limited training, as only a few key parameters need to be provided before it can operate autonomously.

# Key Features
* **Affordable Construction:** By leveraging 3D printing and common off-the-shelf parts, this DIY syringe pump can be built for a fraction of the cost of commercial syringe pumps.
* **Flexible Design, Fine Control:** The design of this pump can accommodate syringes ranging from 10 to 20 mL and dispense volumes as small as 0.0004 mL or 0.0025 mL for the 10 and 20 mL syringes, respectively. When running at the maximum flow rate, however, the contents of each syringe can be emptied in under 6 (10 mL) or 7 (20 mL) seconds.
* **Programmatic and Manual Control Options:** Directional buttons and a potentiometer that controls flow rate allow for manual operation, while a constant flow rate can also be set in the code for automatic operation.
* **Status LED:** A large LED integrated into the electronics housing glows green when the pump is in operation, yellow when the pump is paused, and red when it is out of liquid, allowing for easy identificaiton of the pump's status.

# CAD Model
<iframe src="https://vanderbilt968.autodesk360.com/shares/public/SHd38bfQT1fb47330c99b5e130da64a74320?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

# Operation Instructions
1) Determine the optimal syringe position in the slots on the carriage and end stop so that as much liquid as possible can be dispensed before the carriage triggers the end stop.
2) Before flashing the code to the Arduino, update the SYRINGE_VOLUME_ML, SYRINGE_BARREL_LENGTH_MM, and FLOWRATE_ML_PER_MIN variables with your syringe dimensions and desired maximum flowrate.
3) Use the arcade buttons to position the carriage so that the filled syringe can be inserted. 
4) Set the desired flow rate with the potentiometer knob, checking the output on your computer's serial monitor.
5) Press the latching power button to begin dispensing. The pump will run until the end stop is triggered by the carriage or manually paused with the power button. The pump can be reversed and reset using the arcade buttons.

# Bill of Materials
## Off-the-Shelf Parts

| Item | Quantity |
| --- | --- |
| V-Slot Aluminum Extrusion (20 x 40 x 350 mm) | 1 |
| NEMA-17 Motor | 1 |
| Linear Rod (8 x 200 mm) | 1 |
| Lead Screw (8 x 8 x 250 mm) | 1 |
| Flexible Coupling (1/4" x 8 mm) | 1 |
| LM8UU Linear Bearing | 1 |
| TR8x8 mm Lead Screw Nut | 1 |
| FR688ZZ Flanged Ball Bearing | 1 |
| Lock Collar (8 mm) | 1 |
| Shaft Collar (8 mm) | 2 |
| Elegoo Uno | 1 |
| A4988 Stepper Driver | 1 |
| Limit Switch | 1 |
| Potentiometer | 1 |
| Arcade Button | 2 |
| Latching Panel Mount Button | 1 |
| Common Cathode LED | 1 |
| Breadboard | 1 |
| Mean Well RQ-65D Quad Power Supply | 1 |
| M3 x 10 mm Bolt | 14 |
| M3 T-Nut | 14 |
| M3 x 8 mm Thread-Forming Screw | 4 |

## 3D Printed Parts

| Item | Material | Quantity |
| --- | --- | --- |
| Motor Mounting Plate | ABS | 1 |
| Carriage | ABS | 1 |
| End Stop | ABS | 1 |
| Shaft Collar Retainer | ABS | 1 |
| Electronics Enclosure Box | PLA | 1 |
| Electronics Enclosure Lid | PLA | 1 |
| Potentiometer Knob | ABS | 1 |
| Nameplate | PLA | 1 |

# Arduino Code Repository
The code for the syringe pump can be found [here](https://github.com/kyle-vallone/kyle-vallone.github.io/blob/main/assets/Syringe_Pump_Arduino_Code). Before flashing to the Arduino, be sure to update the SYRINGE_VOLUME_ML, SYRINGE_BARREL_LENGTH_MM, and FLOWRATE_ML_PER_MIN variables for your use case.

# Photo Gallery

