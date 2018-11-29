![Snappy Full Rendering](https://github.com/revarbat/snappy-reprap/wiki/v3.0-snappy_small.png)

Snappy-Reprap 3 Prime
===============

Snappy3 Prime is a variant of Snappy 3 with some model tweaks and firmware changes.

## Firmware Changes

 - All endstops have been inverted, so the endstops correctly report "unpressed" when they are not pressed. Before inversion, the endstops appeared to report "pressed" when they were unpressed, and the motors would refuse to turn backwards (believing the axis was at-home).
 - Heated bed support is disabled. The heated bed thermistor is inactive and overheating protections for the heated bed are off.

## Hardware Choices

 - Endstops: [Gowoops 5 PCS Mechanical Endstop Switch with Cable](https://amzn.to/2ScCRdb)
 - Glass Bed: [Signstek 3D Printer MK2 MK3 Heated Bed Tempered Borosilicate Glass Plate 213x200x3mm](https://www.amazon.com/gp/product/B00QQ5Q3BI/ref=oh_aui_detailpage_o03_s00?ie=UTF8&psc=1)

## Compiling Firmware

The firmware source code is in the `firmware/marlin` directory. To compile and upload the firmware to the Arduino Mega 2560 board, you will need the Arduino IDE with the U8glib library plugin installed. Check out the [RepRap Wiki](https://reprap.org/wiki/Marlin#Configuring_and_compilation) for more details.

## Model Changes

 - X and Y axis motor cages have thinner walls to allow stepper motors with extended cable ports to fit through.
 - Glass bed supports have been slightly extended for a tight fit on the glass bed.
 - Two endstops are required for each rail of the Z axis (not specified in the assembly instructions). These allow the two motors/rail segments to normalize independently.

## Original README

A parametric design for a cheap self-replicating 3D printer (reprap) that snaps together to minimize screws and non-printed parts.

Important Links:

What                 | URL
-------------------- | -------------------------------------------------------
GitHub Repository    | https://github.com/revarbat/snappy-reprap
Project Wiki         | https://github.com/revarbat/snappy-reprap/wiki/v3.0-Home
Bill of Materials    | https://github.com/revarbat/snappy-reprap/wiki/v3.0-BOM
How to Assemble      | https://github.com/revarbat/snappy-reprap/wiki/v3.0-Assembly
RepRap.org Wiki Page | http://reprap.org/wiki/Snappy
Dev Forum            | https://groups.google.com/forum/#!forum/snappy-reprap-dev

[![Join the chat at https://gitter.im/revarbat/snappy-reprap](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/revarbat/snappy-reprap?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)


Generating STL Files
====================
For all platforms, you will need to have OpenSCAD installed. You can download OpenSCAD from their website at [http://www.openscad.org](http://www.openscad.org)


OS X:
-----
Under OS X, you'll need to make sure you have the Xcode command-line tools installed first.  You can get them by installing Xcode from the App Store.

You shouldn't need to change the Makefile.  It should set $OPENSCAD as:
```
OPENSCAD=/Applications/OpenSCAD.app/Contents/MacOS/OpenSCAD
```

To generate the STL model files, open a terminal to the snappy-reprap directory and type:
```
make
```


Linux:
------
Under Linux, you will need to edit the Makefile, and change $OPENSCAD to:
```
OPENSCAD=openscad
```
To generate the STL model files, open a terminal to the snappy-reprap directory and type:
```
make
```


Windows:
--------
Under Windows, you'll probably have to open and compile each `*_parts.scad` file individually and manually export the STL files.

You _might_ be able to run the makefile under CygWin, if you set $OPENSCAD to something like:
```
OPENSCAD="/Program Files/OpenSCAD/openscad.exe"
```

