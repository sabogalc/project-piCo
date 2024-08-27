# Boardview Files

### What is a boardview file?

A boardview file is a netlist of all the connections on a PCB with every component laid out exactly as it is in real life. This is a much more modern and easy approach to viewing connections and approaching troubleshooting than sifting through a schematic to figure out which parts and nets need to be connected to each other.

### How can I view these files?

Much like how there are many PCB EDA softwares out there, there are also many board viewing softwares. The two that I have used and recommend are the MIT licensed [OpenBoardView](https://github.com/OpenBoardView/OpenBoardView) or the commercial (with free version available) [FlexBV](https://pldaniels.com/flexbv/). Below is a screenshot of the Type-C Pico boardview when viewed from FlexBV.

![Pico Boardview](https://github.com/user-attachments/assets/84bf1fcd-a03f-4ae5-9713-422c2b41f7c7)

You can see the VBUS net is selected, and everywhere that VBUS is present on the board lights up in green. There is also a table of every component and its pin number that has VBUS on the right-hand side. Other important information seen in this boardview is the designators for each part, as well as the value of every resistor and capacitor and the footprint for every component.

All of this metadata comes from the `.obdata` file, and as of August 2024, this metadata is only viewable in FlexBV, which is why I use it as opposed to OpenBoardView. However, the `.obdata` file format is an [open file format and initiative](https://openboarddata.org/), and I would very much like to see the feature added to OpenBoardView.

### How can I make boardview files for my own designs?

All of the boardview files I make for my projects are using [an open-source KiCad plugin](https://github.com/whitequark/kicad-boardview). When I first came across this plugin, it had a few bugs with current versions of KiCad, so I submitted some pull requests and the plugin is back into perfect operating condition. The `.obdata` generation script is currently internal since I made a bit of a mess [submitting that PR](https://github.com/whitequark/kicad-boardview/pull/16), but I am looking to release it eventually.