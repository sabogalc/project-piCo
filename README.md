# project piCo

This repository contains KiCad project files for reverse-engineered Raspberry Pi Pico boards, including both the standard Pico H and the WiFi version, the Pico WH. The primary goal of this project is two-fold:

1. USB-C Upgrade: Although all Pico boards were released in or after 2021, they all use Micro-USB. The initial aim was to update these boards to include USB-C, making them more compatible with modern standards.

2. Accessibility of Design Files: During this process, I discovered that the original board designs are created in Cadence Allegro, a format that is less accessible due to its encrypted file structure and the expensive software required. This project not only adds USB-C support but also aims to make the design files as free and open as possible.

For detailed information on each board’s design, please refer to their specific folders within the `KiCad Projects` directory. Boardview files for all boards, including the original Pico H, are provided to allow for easy troubleshooting. The designs in this repository are freely available for use without any license restrictions or attribution requirements.

> The USB-C version of the Pico H board. The layout for this board differs slightly from the original.
![image](https://github.com/user-attachments/assets/3d2943af-c4f5-4dba-b2e3-bb380a24210b)

> The USB-C version of the Pico WH board, a much closer recreation of the original board.
![image](https://github.com/user-attachments/assets/429d3ffc-f5d3-4d9b-a8b5-73fd3a04eb2a)