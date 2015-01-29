SatNOGS Arduino
===============

Repository of Arduino code and Arduino PCB for SatNOGS project.
Refer to block diagram in the repository for wiring documentation.

Electronics and code are modified to work with a bare AtMega328p with the Arduino Bootloader. This spares buying the Arduino Micro. The stepper motor drivers are replaced by DRV8825 modules (Drop-in replacement part) from eBay.

This will be used in our costumized version of the SatNOGS PCB for the High Altitude Object Tracker, which will be part of the SatNOGS project as well.

# Flashing Instructions

Use the following command line to ISP the AtMega328p from an AVR910

avrdude -cavr910 -b115200 -P/dev/ttyUSB1 -pm328p -U lfuse:w:0xFF:m -U hfuse:w:0xDE:m -U efuse:w:0x05:m -v -x devcode=0x31

avrdude -pm328p -b115200 -cavr910 -x devcode=0x31 -P/dev/ttyUSB0 -U flash:w:SatNOGS.hex -v
