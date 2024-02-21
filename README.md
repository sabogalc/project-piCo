# project-piCo

This is a fully reverse-engineered Raspberry Pi Pico H made in KiCad version 7. The Raspberry Pi Foundation publishes lots of information on this board, including the full schematics and board layout files. However, they're made in Cadence Allegro, and that costs a crisp $1,500/month that I do not have.

Originally, I just made a PCB that jumped the Micro-USB signals to a Type-C breakout board, but the tolerances were really tight, and it didn't look like much of a finished product. My boss gave me the idea of just remaking the whole board and adding a Type-C port to it, so that's what I did.

I took the schematic from [here](https://datasheets.raspberrypi.com/pico/pico-datasheet.pdf#page=26) and the PCB design files from [here](https://datasheets.raspberrypi.com/pico/RPi-Pico-R3-PUBLIC-20200119.zip) (Warning, the second link will instantly download the schematic and board layout instad of previewing it). I also found a webpage that had the BOM for the Pico, which you can find [here](https://archive.is/NHUY5).

The mechanical layout provided by the Pi Foundation was extremely useful in creating my board dimensions. Since my footprint was made in KiCad, anybody should be able to implement it for their own projects.

> Note - this project contains a footprint called "CON_PICO_40W" that is an exact replica of the original footprint, but I used a modified version for my board called "CON_PICO_40W_VER_C". I will highlight the differences below.

![image](https://github.com/sabogalc/project-piCo/assets/53708281/e2d75217-aeb5-4e7a-b6b1-d67d2e49ab80)

Version 1 of this board had many issues. You can see that version by either viewing the commit history or by viewing the archived version [here](https://archive.is/PpIPD). One of the biggest issues was the size constraint of adding a Type-C port to the original footprint.

When I published this project, many people let me know that Type-C Pico clones already exist. As such, I modeled my redesign after one of these clones, and that was the purple board from [this AliExpress listing](https://www.aliexpress.com/item/3256805444428998.html).
![image](https://github.com/sabogalc/project-piCo/assets/53708281/160bd96f-20e4-46b0-b705-9c5adce5a875)

Removing the 4 holes and adding space at the top for the Type-C port vastly improved my ability to design and route this board, so the "CON_PICO_40W_VER_C" used in this revision is a copy of the purple clone board. Sometimes you just need to [reverse-engineer the reverse-engineers](https://youtu.be/FVEQJNRmfDQ?t=431).

The boot select switch, Schottky diode, and 12MHz crystal in my design differ from the ones in the original since I could not find them in stock, but they should be plug-and-play substitutes.

For those of you without KiCad or that just want to take a quick look at the schematic, [here](https://github.com/sabogalc/project-piCo/blob/main/Pico%20C/RPI-PICO-R3a-PUBLIC.pdf) is a link to a PDF copy of the schematic.

Below is a 3D render of my board. This version 3 board is much better than the original, but it is still not quite up to par with the real Pico. Namely, my board does not use as many power planes as the original version (I have one plane for 3.3V and another for GND). Also my USB D+ and D- traces aren't signal paired, but I honestly think they're close enough to where there will be no issues in real-world use cases.

![image](https://github.com/sabogalc/project-piCo/assets/53708281/f7d44c88-a138-4fb8-89ac-43ebd6b3b42a)

Compared to [version 2](https://archive.is/ivA9B), version 3 has improvements in silkscreen labeling of the pins, the LED, and the USB connector. It also has a 3.3V copper pour on the top layer of the board, which improves the 3.3V routing tremendously. Further improvements could be made in having more power plane pours, but this version should be relatively solid.

As before, I would happily accept pull requests to improve this design. My main grievances with this board are as follows:
- Better routing for the power rails (e.g. more pours rather than tracks)
- Finnicky routing needed in some areas (e.g. frequent jumps between board layers to avoid overlaps)
- Optimizing of component placement to be able to have more pins with silkscreen numbers next to them

I would also be interested in replacing R11 with a LM4040 shunt voltage reference. For now, I wanted a board that had all of the same components as a real Pico so that I could just swap them over, but adding the voltage reference would help make my design an improvement over the original.
