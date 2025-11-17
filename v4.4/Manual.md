# A2DVI.v4.4: Digital Video card for Apple II Computers with multifunction capabilities

## Preface

This is a firmware project for a digital DVI/HDMI video card for Apple II. It directly produces a digital video stream from the Apple II's memory content. The signal is output via an HDMI connector, connecting the Apple II to modern displays with HDMI (or DVI) inputs. No more analog signal conversion required.

The project is a collaboration of Ralle Palaveev and Thorsten Brehm. 

The hardware is based on the PICO controller board. Both, original PICO (RP2040) and newer PICO2 (RP2350) modules are supported. Separate firmware is provided for the two PICO variants.

The initial designs v1.x and 2.x have been unidirectional where the card is snooping on the A2 computer address, data and control buses and creates a shadow image of what is to be displayed. The image is then sent to the HDMI output as digital video. More information on the technology is here: https://github.com/ThorstenBr/A2DVI-Firmware

Version 4.x of the card is now bi-directional as well as the hardware is directly manufactured with a RP2040 processor on board, instead a RPI Pico.

This new design allow for housing of programs on the card which can communicate back and forth with the A2 computer. This has allowed for several firmwares to be pre-loaded on the card and each one can be used at a time, turning the card into a specific functional card.

## Firmwares on the card

Currently there are 5 firmwares on the card:

1. A2DVI - HDMI video display adapter
2. Z80 emulator for Applicard CPM
3. Apple II Mouse (PAL) - an adapter for a USB mouse for Apple2 for PAL video timing
4. Apple II Mouse (NTSC) - an adapter for a USB mouse for Apple2 for NTSC video timing
5. USB Floppy Disk II

Only one firmware is active at a time. A firmware can be selected from an initial selection menu, which can be invoked within 15 seconds of powering the computer by calling PR#N command, where N is the slot number.

Once the computer is powered, DVI is always active during the 15s timeout, so that the user can see the menu for firmware selection. If the DVI firmware is not the one to be active, the bottom of the screen displays which firmware would become active and the timeout counter. During the initial 15s timeout the LED blinks very fast.

Once a firmware is selected, the timeout ends immediately and the selected firmware becomes active.

If during the 15 second timeout nothing is done, upon timeout completion the previously selected firmware becomes active.

If cold reset is performed (Ctrl-OpenApple-Reset), this does not affect the function of the firmware - the timeout is not invoked. It is only active after a power on.

Each firmware function is described below.

1. A2DVI. All functions are the same as described in the original design of version 2.x: https://github.com/ThorstenBr/A2DVI-Firmware The only difference is that by running PR#N, while DVI is active, the DVI configuration menu would be started. During DVI function the LED blinks fast.

2. Z80 emulator for Applicard CPM. If this mode is selected, then the user can boot Applicard CPM, an example disk is here: https://github.com/rallepalaveev/A2DVI/blob/main/v4.4/PCPI%20AppliCard%20D1.po Suggested card slot: 4.

3. and 4. Apple II Mouse Card (PAL and NTSC). This firmware turns the card into a Mouse controller - it has to be installed in Slot4 and a USB mouse connected to the USB-c port of the card (an adapter may be needed for USB-A mouse). Once the firmware becomes active (15s after power-on)

5. When FDD is selected, the LED blinks slow until the 2 floppy disk images are selected; calling PR#N displays a menu to select disk images for the 2 floppy disk drives. The 140kB .dsk images must be on a thumb drive connected to the USB-c port of the card. After selecting the disk images, the LED blinks synchronously with the floppy disk access.

If programs require to change disks:
The current solution is to connect an external button (A2DVIplus has a two pin connector to connect a button/switch). The firmware detects floppy images with names only differing in a single digit. So, the trick is to prepare the disk images to follow a naming scheme. "Oregon Trail - Disk1.dsk", "Oregon Trail - Disk 2.dsk" etc. Then you just select the boot disk via the menu. And when the program later asks to flip/cycle disks, you simply press the button to advance one digit ahead. The firmware automatically cycles through the disk images - in ascending order. Just sometimes requires a bit of preparation. Something like "Prince of Persia (boot disk).dsk", "Prince of Persia (side a).dsk" doesn't work, so some images need to be renamed.
