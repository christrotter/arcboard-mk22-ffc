# arcboard-mk22-ffc
![Render](images/render.png)
FFC wiring harness for the Arcboard mk22's [mainboard](https://github.com/christrotter/arcboard-stm32-mk2).  Hooks up a whole pile of keys, peripherals, and indicators with a single cable.  

The goal was to reduce manual soldering as much as possible while also reducing the number of FFC's coming off the mainboard.  [The old mainboard](https://github.com/christrotter/arcboard-stm32) had 10 FFCs coming off at all angles and it was a nightmare to install.

## ordering
**VERY IMPORTANT:** This FFC design lacks stiffeners, and this is by design!

Because the 0.3mm-pitch connectors require thinner stiffener, and we're using 0.5mm-pitch connectors for everything non-Cyboard, I need to use EasyEDA to do the final work.
Why?  Because not only does JLC prefer it, but it allows you to specify metadata on each stiffener, like material and thickness.  

Giant premise: You can do different stiffener types in a single board.  I am hopeful of this because their docs show that you can use different materials.  It stands to reason different thicknesses is also ok.

Specifically, the different pitch sizes require different total FFC thicknesses.
- 0.3mm-pitch -> 0.2mm thick FFC, including stiffener
- 0.5mm-pitch -> 0.3mm thick FFC, including stiffener (connector specs range from `0.27-0.33mm` to `0.29-0.31mm`)

I'll write up more detail about the EasyEDA process once done.

## peripherals
But what peripherals does this hook up?
- six [Cyboard column PCBs](https://cyboard.digital/products/dactyl-flex-pcbs)
- five [Cyboard thumb key PCBs](https://cyboard.digital/products/dactyl-flex-pcbs)
- [main LED indicator PCB](https://github.com/christrotter/para-led-ogram)
- [ring gear encoder indicator PCB](https://github.com/christrotter/ring-led-pcb)
- [an ST7789v2 LCD adapter PCB](https://github.com/christrotter/lcd-adapter-pcb)
- [two led-backlit EC10 encoders](https://github.com/christrotter/top-encoder-pcb)
- [one non-lit EC10 encoder](https://github.com/christrotter/mouse-encoder-pcb)
- [STM32 mainboard](https://github.com/christrotter/arcboard-stm32)
- [a dpad (5-way)](https://github.com/christrotter/led-pad)
- [three paddles (3x 5-way)](https://github.com/christrotter/multi-paddle-pcb)
- [PMW3360 to FFC](https://github.com/christrotter/charybdis-pmw-3360-sensor-pcb/tree/arcboarding) (*forked from* [Charybdis](https://github.com/Bastardkb/charybdis-pmw-3360-sensor-pcb))

![Front and back](images/render-front-back.png)

## development notes
- A lot of paper and tape was used.
- I printed out both right and left halves, plus printed the mainboard step file in PLA, plus made a mirror-able jig to mimic the shell
- Then a lot of fiddle-faddling, taping it in place, folding it, bending it, cutting/adjusting... a week or two of this.

[Mapping out the FFC in detail.](https://docs.google.com/document/d/1AaeZN3C4SzMbZbiK-B96kASK0Lhcgzr27FD6T2ESAdA/edit?usp=sharing)
[The build journal - in great detail.](https://docs.google.com/document/d/1yYdNSWEpefUsuglO4ZzcITcItB_Wx3liXkT57BLO2Ac/edit?usp=sharing)

### what if only one half has a trackball?
The theory is I tape or cap off the PMW endpoint on the left half.

## schematic
![Schematic](images/schematic.png)

## PCB layout
![PCB layout](images/pcb-layout.png)

## other
This is a FFC (flat flexible cable) or FPC (flexible printed circuit) - I am uncertain which term is right, so I go with FFC.
