# FAULT, ERRORS and IMPROVEMENTS on HexAgon v1 hardware

## Errors
* EZ80 MISO and MOSI reversed - fixed in KiCAD
* Y1 and Y2 crystals replaced by mainstream versions - fixed in KiCAD
* 10k pull-ups on rcNMI, rcBUSREQ, rcWAIT to 5V. To prevent CMOS current draw and contention.
* 10k pull-ups on rcD0...rcD7 and U17 /OE==L when CS1=active or CS2=active or CS3=active => /CS1 && /CS2 && /CS3 = /OE. So data is always output if /RD=H and only input when /RD=L and CS1/2/3 is active L. To prevent CMOS current draw and contention.
* Add a jumper to connect +5Vrc to +5V_USB (via 1N5819S4/SOD123) to allow powering the bus via USB or the bus powering HexAgon. The level-shifters need a stable VccA and VccB

## Part ordering mistakes
* replace 0.1uF 100VDC 20% for a 6.4V model - c12, c11, c66, c20, c21
* 100nF/10V/20%/X5R/0402 ordered wrong GRM022R61A104KE01L should be:
* ZDI1 connector wrong, 90130-1206 is too narrow => using pinheaders instead
* J3 connector wrong, ordered gold pinheader, should be double row 02x16, smd 
* UEXT1 part wrong, 2x5 angled header is straight header
* Micro_SD1 part wrong DM3D-SF(41) => TFC-WPAPR-08-LF

## Optimisations
* reduce amount of different components
* bss138 FET + resistors replace with 5v-3.3v level shifter or double fet package
* ZDI, ZCL signals connected to ESP32?
* replace the 5Mhz base clock crystal with a integer division of 36.864.000 Mhz => 3.686.400 Mhz * 10 for more optimal standard baudrates
* Micro_SD1 Olimex TFC-WPAPR-08-LF footprint => order from Olimex => or replace by DM3D-SF(41) or 1140084168
