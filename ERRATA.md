# FAULT, ERRORS and IMPROVEMENTS on HexAgon v1 hardware

## Errors
* EZ80 MISO and MOSI reversed
* replace 0.1uF 100VDC 20% for a 6.4V model - c12, c11, c66, c20, c21
* Y1 and Y2 crystals replaced by mainstream versions
* 100nF/10V/20%/X5R/0402 ordered wrong GRM022R61A104KE01L should be:
* ZDI1 connector wrong, 90130-1206 is too narrow => using pinheaders instead
* J3 connector wrong, ordered gold pinheader, should be double row 02x16, smd 
* Micro_SD1 part wrong, expected 9 pin Signal + 4 pin GND, is 8 pin Signal + 4 pin GND => DM3D-SF(41) or 1140084168
* UEXT1 part wrong, 2x5 angled header is straight header

## Optimisations
* reduce amount of different components
* bss138 FET + resistors replace with 5v-3.3v level shifter or double fet package
* ZDI, ZCL signals connected to ESP32?
* replace the 5Mhz base clock crystal with a integer division of 36.864.000 Mhz => 3.686.400 Mhz * 10 for more optimal standard baudrates
