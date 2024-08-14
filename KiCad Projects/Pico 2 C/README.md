# project piCo 2

I was extremely excited to see the announcement of the Pico 2 last week, but some of my enthusiasm left me when I saw that the new board still retained the Micro-USB connector. Of course, I got right to work on correcting this issue.

### Design Sources

Despite the online documentation and datasheet linking to design files for the board, the link appears to be broken as of August 14, 2024. (See [this issue](https://github.com/raspberrypi/documentation/issues/3809) for more information)

Still, I worked with the schematic and pictures of the board to be able to create an initial version of a Type-C Pico 2.

- **Schematic:** [Raspberry Pi Pico 2 Datasheet](https://datasheets.raspberrypi.com/pico/pico-2-datasheet.pdf#page=23)
- **PCB Pictures (Front & Back):** [Pico 2 PCB Photos](https://blog.zonepi.cz/rapsberry-pi-pico-2/)

Thankfully, with all the work I've already done on reversing the Pico, making this board was a breeze as I was able to reuse many of my assets and resources from the previous boards.

### Design Process

Kicad allows for Reference Images to be placed while routing a board (found in `Place > Add Reference Image`), so I put the aforementioned scans into the project to scale, and based my routing on the photo. This means that my board is not fully 1:1 with the factory one, but in lieu of the official design files, this was the best that could be done right now. An example of this layout is shown below.
![Screenshot 2024-08-14 010045](https://github.com/user-attachments/assets/0f120da2-34e5-4181-9526-98ada7147475)

### Component Substitutions (IMPORTANT)

As-is, this board is not ready for production. I was unable to figure out what component or footprint L2 is, other than that it is a coupled inductor and measures roughly 1.75x2.2mm. As a stand-in, I have placed an 0602 SMD inductor, but please note that this is **_not correct_**. As before, the boot select switch and 12MHz crystals are compatible substitutes (even though they told us what crystal was used this time, I just reused the asset I already had from the previous design).

### PDF Schematic

A PDF copy of the schematic is available [here](https://github.com/sabogalc/project-piCo/blob/main/KiCad%20Projects/Pico%202%20C/Pico%202%20C.pdf).

### Board Photos

Because of the aforementioned inductor issue, the only photos of this board right now are the KiCad renders. If anybody figures out what inductor this is, please either let me know or make a correction in the form of a pull request.

![Screenshot 2024-08-13 221337](https://github.com/user-attachments/assets/5c379148-97d2-4de6-bff9-8b9d4813766e)
![Screenshot 2024-08-13 221413](https://github.com/user-attachments/assets/6a45b8de-724e-4385-8815-d248af0ea741)