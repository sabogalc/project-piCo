# project piCo W

After a few months of making projects with the Pico, I found myself wanting to utilize some of the features offered by the Pico W. However, this meant that I would need to give the same USB-C reverse-engineering treatment to this board, so I took what I learned from my first go and remade the Pico WH as best I could. 

### Design Sources

- **Schematic:** [Raspberry Pi Pico W Schematic](https://wiki.amperka.ru/_media/products:raspberry-pi-pico-w:raspberry-pi-pico-w-schematic.pdf)
- **PCB Design Files:** [RPi PicoW Files](https://datasheets.raspberrypi.com/picow/RPi-PicoW-PUBLIC-20220607.zip) (Note: This link will download files directly.)

This time, rather than making my own board layout, I tried to follow the factory layout as closely as possible. Similarly to the [Official Files](https://github.com/sabogalc/project-piCo/tree/main/KiCad%20Projects/Pico%20C#Official%20Files) section of the original Type-C Pico, I converted the factory Allegro files into a KiCad file (with an Altium conversion in between the two).

![Converted Design Close-Up](https://github.com/user-attachments/assets/dbfd9da0-687e-4050-bb36-6c9c7e21ae76)

I then used this converted board as the starting point for my board, so the final result is much closer to the original design. Unfortunately, I cannot release either the converted board or my initial design at this time for reasons that I will explain below.

### The Patent

On page 2 of the schematic, there is a note by the antenna arrangement that reads
> The Niche is an Abracon/Proant patented antenna technology. Please contact niche@abracon.com for information on licensing.

I sent an email explaining my project and how it wasn't commercial in any capacity, asking if there was any kind of fee I could pay to be able to release the board as is. The reponse I got read

> The licensed version of Niche is aimed for high volumes (>100kpcs), and there is a royalty fee/pcs which is agreed per project/customer. The idea is that it should be a very cost-effective solution for high-volume production. It is not an open-source solution which can be used without agreement with Abracon.

They did offer an alternative in the form of a stamped metal antenna that worked virtually identically and came with no license requirement, so I remade the board around this footprint (which is the one you can find in this folder). I found the patent [here](https://patentimages.storage.googleapis.com/39/da/99/a6a16469f1c9ba/US10910715.pdf), and though I am not a legal or patent expert, my understanding is that by 35 U.S.C. 154(b), this patent will expire on March 11, 2038, after which I will be okay to release all of the designs.

### Design Process

Though I am not releasing the design that is barred by the patent, I will still show photos of the final version of that board, and I have also released the boardview file for that board (neither one of these are remotely close to a finished PCB, so I'm sure that is fine). Below is a photo of both boards, with the royalty-free design on the left and the closer 1:1 design on the right.

![image](https://github.com/user-attachments/assets/96915182-8995-4ed1-ae97-e3a778f97d2f)


My design process was essentially Alt+Tabbing between a window that had the converted Allegro design and my blank PCB and just building it up piece by piece while following the design specifications from the import. I did have to make some changes in order to get the board manufactured such as slightly decreasing the diameter of the BGA balls for the WiFi chip, but the final result is still very close to the original parameters.

Unfortunately, because of how many vias this board has, the tight routing, and the fact that it is four layers, it costs about $70-75 USD to get 10 of them manufactured, and then to be able to populate them raises the price even more, so it is not very financially sound to order and make this board. Regardless, these design files should still prove useful as an educational resource.

### Component Substitutions

As with the original project piCo, the boot select switch, Schottky diode, and 12MHz crystal in my design are not the exact ones that the Pi Foundation used, but they are compatible substitutes.

### PDF Schematic

A PDF copy of the schematic is available [here](https://github.com/sabogalc/project-piCo/blob/main/KiCad%20CProjects/Pico%20WH%20-%20No%20License/Pico%20WH.pdf).

### Board Photos

Below are the renders of the board in KiCad, as well as individual photos of them in real life.

- **KiCad Render - Original:** ![KiCad Render - Original](https://github.com/user-attachments/assets/f927ef53-5a95-45bc-8825-e9c26552cad8)
- **KiCad Render - No License:** ![KiCad Render - No License](https://github.com/user-attachments/assets/5ddd6fba-bcf6-49d5-841d-96c9bb45576e)

- **Pico WH:** ![Pico WH](https://github.com/user-attachments/assets/ce3e4846-1aaa-4193-b0c0-4a86980cd7de)
- **Pico WH - No License:** ![Pico WH - No License](https://github.com/user-attachments/assets/d4c077f3-50ab-40ce-b2ea-31a2d3b9cd26)

### Future Enhancements

A version of this board with a non-patented antenna could be developed. Similar designs are available in Chinese clone boards, such as the one in [this AliExpress listing](https://www.aliexpress.com/item/3256805996726845.html). If anyone would like to submit a pull request with changes like this one, I would be happy to merge it.

![Pico W Clone](https://github.com/user-attachments/assets/8b852baa-0e5b-403c-9039-d043709eadbc)