# project piCo

This is a completely reverse-engineered Raspberry Pi Pico H made in KiCad version 8. The Raspberry Pi Foundation offers schematics and board layout files for the original board, but they are made in Cadence Allegro, which costs a crisp $1,500/month that I do not have. Instead, I opted to recreate the board in KiCad so that I could add a Type-C port.

### Overview

Initially, I developed a PCB to convert the original Micro-USB signals to a Type-C breakout board. However, the tolerances were really tight, and it didn't look like much of a finished product. My boss gave me a suggestion to redesign the entire board and add a Type-C port to it, which is what I ended up doing. I started the process with the original design files, which you can find in the section below.

### Design Sources

- **Schematic:** [Raspberry Pi Pico Datasheet](https://datasheets.raspberrypi.com/pico/pico-datasheet.pdf#page=26)
- **PCB Design Files:** [RPi Pico R3 Files](https://datasheets.raspberrypi.com/pico/RPi-Pico-R3-PUBLIC-20200119.zip) (Note: This link will download files directly.)
- **BOM:** [Pico Bill of Materials](https://archive.is/NHUY5)

The mechanical layout provided by the Pi Foundation was extremely useful in creating my board dimensions. Since my footprint was made in KiCad, anybody should be able to implement it for their own projects.

### Footprint Differences

The project includes a footprint named "CON_PICO_40W," which replicates the original footprint, and a modified version, "CON_PICO_40W_VER_C," which is used in my design. Key differences are highlighted below.

![Footprint Image](https://github.com/sabogalc/project-piCo/assets/53708281/e2d75217-aeb5-4e7a-b6b1-d67d2e49ab80)

### Design Evolution

Version 1 of the board had many issues. You can see that version [here](https://github.com/sabogalc/project-piCo/tree/4ffbc08c13815f0195cdc85224667cf2c5e13563). The biggest challenge was fitting the Type-C port within the original dimensions.

When I published this project, many people let me know that Type-C Pico clones already exist, so I modeled my redesign after the purple clone board from [this AliExpress listing](https://www.aliexpress.com/item/3256805444428998.html).

![AliExpress Board](https://github.com/sabogalc/project-piCo/assets/53708281/1c073767-9edb-4e5f-8591-c8f2ccd30e73)

The revised design removed the 4 mounting holes and added space for the Type-C port, which vastly improved my ability to design and route this board. The "CON_PICO_40W_VER_C" footprint used in this revision is a copy of the purple clone board. Sometimes you just need to [reverse-engineer the reverse-engineers](https://youtu.be/FVEQJNRmfDQ?t=431).

### Component Substitutions

I could not find the original boot select switch, Schottky diode, or 12MHz crystal in stock anywhere, but the substitutions I made should be plug-and-play.

### PDF Schematic

For those of you without KiCad or that just want to take a quick look at the schematic, a [PDF version](https://github.com/sabogalc/project-piCo/blob/main/KiCad%20Projects/Pico%20C/RPI-PICO-R3a-PUBLIC.pdf) is available.

### Version 4 - A 1:1 recreation

[Version 3](https://github.com/sabogalc/project-piCo/tree/0116e01858a51d29eb83f16cde15d637a825e509) of this board improved on [version 2](https://github.com/sabogalc/project-piCo/tree/e2333728981e60bb3f34c05a658cf739d1d45163) in regards to copper pours, routing, and silkscreen labeling. However, versions 1-3 were all routed from scratch by myself. As seen below in the `Official Files` section or in the [piCo W folder](https://github.com/sabogalc/project-piCo/tree/main/KiCad%20Projects/Pico%20WH%20-%20No%20License), I later learned how to convert a Cadence Allegro board into a KiCad one, and this allows me to make a 1:1 PCB when reverse-engineering. Version 4 is this 1:1 render, and it should theoretically be the last version of this board.
![Version 4 Render](https://github.com/user-attachments/assets/22a4bc11-2788-4109-a861-58439af590a5)

When it comes to improving the Pico, I have thought about making design improvements to the ADC or adding a reset switch. However, the overall purpose of this project is to be 1:1 with the layout and parts of an original Pico, though if anyone finds any room for improvement I would be happy to make any fixes (e.g. the grid on the schematic is not standard and could use correction).

_**DISCLAIMER**_

I have interned at this company for almost two years.

For those of you that want a board with the aforementioned improvements, check out the [RP2040 board from Out of the Box](https://www.ootbelec.com/store/p/ootb-rp2040).

### Official Files

I have updated this folder to include a file called `RPI-PICO-R3a-PUBLIC - Official.kicad_pcb`. This is as close to the original Cadence Allegro design file that I could get imported into KiCad. I first converted the Allegro board into an Altium one, and then I converted the Altium board into KiCad.

![Converted Design](https://github.com/sabogalc/project-piCo/assets/53708281/2ef8d706-aa4e-4265-992c-f2f538ea8131)
![Coverted Design Close-up](https://github.com/sabogalc/project-piCo/assets/53708281/453bdc88-b8c0-4084-bf2b-c5cee0fe55d0)