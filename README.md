# project-piCo

This is a fully reverse-engineered Raspberry Pi Pico H in KiCad version 7. The Raspberry Pi foundation publishes lots of information on this board, including the full schematics and board layout files. However, they're made in Cadence Allegro, and that costs a crisp $1,500/month that I do not have.

Originally, I just made a PCB that jumped the Micro-USB signals to a Type-C breakout board, but the tolerances were really tight, and it didn't look like much of a finished product. My boss gave me the idea of just remaking the whole board and adding a Type-C port to it, so that's what I did.

I took the schematic from [here](https://datasheets.raspberrypi.com/pico/pico-datasheet.pdf#page=25) and the PCB design files from [here](https://datasheets.raspberrypi.com/pico/RPi-Pico-R3-PUBLIC-20200119.zip) (Warning, the second link will instantly download the schematic and board layout instad of previewing it). I also found a webpage that had the BOM for the Pico, which you can find [here](http://www.ntpcb.com/simple/?t175138.html).

The mechanical layout provided by the Pi foundation was extremely useful in creating my board dimensions. Since my footprint was made in KiCad, anybody should be able to implement it for their own projects. For the four 2.1mm holes on the front and back of the board, I believe I left too much copper exposed because the Pico has almost no visible copper in these holes, but I believe that everything else is well within spec.
![image](https://github.com/sabogalc/project-piCo/assets/53708281/e2d75217-aeb5-4e7a-b6b1-d67d2e49ab80)

The boot select switch, Schottky diode, and 12MHz crystal in my design differ from the ones in the original since I could not find them in stock, but they should be plug-and-play substitutes. Additionally, because the Type-C port is larger than Micro-USB, the entire board is pushed back and many things fit with less leeway than I was expecting.

Below is a 3D render of my board. It's okay for my needs, but it's far from the actual Pico. The original one uses copper pours very strategically and has great routing, but the routing on mine is atrocious. The DRC check also gives this board 41 errors and 13 warnings, but I simply elected to ignore them.

![image](https://github.com/sabogalc/project-piCo/assets/53708281/3ee0edff-3ca4-4e53-8b5b-fa1b2015f824)

I would happily accept pull requests to improve this design. My main grievances with this board are as follows:
- Poor routing and copper pour usage
- Overlaps on the Type-C connector's mounting holes and the Pico's holes
- Lots of layer jumping rather than mainly top layer tracks and bottom layer tracks
- Not much attention paid to track thickness or signal pairing
- DRC errors on clearance and unconencted signals
- "LED" silkscreen is upside down relative to the real Pico and that just bothers me.

For all I know this may not even be a functioning board. I released all of these files before I even received a board. I would love to see this project in a more polished condition, but I was happy releasing it as is for now.
