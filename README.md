# EZ-Dipole

![EZ-Dipole mounted with magnetic base on camera mount](images/IMG_20231229_100742.jpg?raw=true "EZ-Dipole mounted with magnetic base on camera mount")            |  ![EZ-Dipole S-Parameter measurement](images/IMG_20231229_104142.jpg?raw=true "EZ-Dipole S-Parameter measurement")
:-------------------------:|:-------------------------:

## Story
So I designed this antenna by using a "standard" dual-band Dipole design (using sleeving bars). This antenna acts as a dipole at 2m, and as a dual-endfed-halfwave at 70cm giving about 3dB of gain. Dipole wires are just 2mm diameter spring steel held in place using some 3D prints. I added 2mm Bullet connectors right at the PCB to make them removable (e.g. for transport).

I feed the dipole from a single-ended coax using a marchand balun. This is a type of balun usually used on PCBs (or MMICs) consisting of coupled lines. By choosing the correct even/odd impedances (essentially trace widths) and trace lengths, you can achieve a very broadband balun. In fact, in theory this balun has to transmission poles that are spaced at fcenter/2 and 3*fcenter/2 which fits perfectly into the 70cm/2m band if the designed center frequency is around 290 MHz. You can find some info on [Microwaves101](https://www.microwaves101.com/encyclopedias/marchand-balun) or in [Electronics page 142](https://www.worldradiohistory.com/Archive-Electronics/40s/Electronics-1944-12.pdf).

In one of the last images you can a rough measurement on the balcony, not perfect for antenna characterization but close enough. You can see that -20dB S11 is achievable in both bands. That is around VSWR 1.2.
The PCBs were manufactured at JLCPCB and cost a maybe 10-20 bucks for a five-pack. The design is published in the ``kicad`` folder and can be directly ordered from JLCPCB for a few bucks.

CAD data for interactive viewing and export is available [here](https://cad.onshape.com/documents/8bec165c172f3d5d236466bc/w/3552c482374d0af884c64410/e/ade224930e898bb7b68000cc?renderMode=0&uiState=65900c81cb4b177d9640ea59). Btw, you can also use this balun for a 70cm-only antenna, then the dipole length is only one third of what you can see in the picture. 2m-only is not recommended, because the sleeving bars give some mechanical rigidity to the long dipole wires. The entire design is currently proof-of-concept, so there is no shell/case and some of the CAD parts will probably be improved in the future.

## Why?
Firstly, I was curious what the performance would be. But along the way I found a few nice things about it.
For example, the dipole bars are grounded. This means, you can connect a lightning arresting connection from the PCB ground plane directly to the ground of your house. The SMA connector center pin is floating (and on the opposite side of the PCB), so this can potentially give your radio a lot of protection from the environment if we add a TVS protection circuit.
Secondly, the quality of the 180 degree phase shift at the output of the balun is very good, so there is virtually no issue with currents running on the outer sheath of the coaxial cable back to the radio and radiate uncontrollably.

## Dual-Band Dipole
Length (End-to-End) for a (spring steel) wire with 2mm diameter
- According to simulation 976mm and 2x316mm
- With a bit of trying out, I selected 980mm and 2x316mm so very close to simulation
You can either start with 990mm and 320mm and try optimizing yourself (if you have a VNA) or just select those values and call it good enough.

## Balun
See input side, output side and rear mount here:

![Balun input side](images/IMG_20231229_101317.jpg?raw=true "Balun input side")

![Balun output side](images/IMG_20231229_101331.jpg?raw=true "Balun output side")

![Balun rear](images/IMG_20231229_101429.jpg?raw=true "Balun rear")
