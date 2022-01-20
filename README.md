# Origins — "Power R, Inc."
Some time in 1988 a video output adapter was produced for early Macintosh compact computers by what I can only assume was
a small company. Records about Power R seem scarce, but it appears they operated for almost exactly 13 years between late
1989 and late 2002. The company was [registered to a James Baker](https://opengovwa.com/corporation/601202550) with an
address in southern Seattle. 

[Modest Googling](https://allpeople.com/james+baker_power-r-inc_1C-us) indicates the company also employed a Kevin 
Connelly, who lists himself as a Lead Electronic Technician, but it appears it was nearly a decade after the release of 
the model in my posession. Copies of their early website is available on [wayback machine](https://web.archive.org/web/19981206112312/http://www.powerr.com/).

# What is it?
<a href="https://github.com/Stephen-Arsenault/compact-mac-video-output/blob/main/images/Power%20R%202702%20(unmodified).jpg?raw=true"><img align="left" width="300" height="400" src="https://github.com/Stephen-Arsenault/compact-mac-video-output/blob/main/images/Power%20R%202702%20(unmodified).jpg?raw=true" style="margin-right: 1em; margin-bottom: 1em;"></a>
 
The Power R 2702 adapter transmits video information from the logic board with slight massaging and is plugged between 
the logic board connector and the logic board. All signals normally passed into the logic board cable are passed through
the adapter so that they continue to work uninterrupted.

The board itself has a 5-pin female header which uses 4 of the pins for Ground, Video, Vertical Sync, and Horizontal Sync.
Early compact Macs transmitted their video signal inverted. For example, this means the while blinking floppy disk is 
rendered as a black blinking floppy disk. The adapter inverts the signal so that the output is normal.

Power for the board is provided by a LM340L ([datasheet](https://www.ti.com/lit/ds/symlink/lm140l.pdf?ts=1637472778366))
from the 12V rail of the logic connector. In fact, aside from a few passives, the construction of the Power R 2702 is very
basic. So basic that the hardware is concealed in epoxy potting. 

As far as output goes, it appears that the adapter did something comparable to Sony Standard or a CGA derivative. I am not
familiar with early modern signals (nor contemporary signalling) — if anyone is more familiar with the specs below I
encourage them to comment!



### Signal Specifications
 - **Resolution**
   - 512 x 342
 - **Horizontal Scan Rate**
   - 22.5 kHz 
   - 4μs on, 40μs off
 - **Output Levels (All Lines)**
   - TTL Positive
 - **Video Connector Pins (DB9)**
   - 1,2 GND
   - 3,4,5 RGB
   - 8 Horizontal Sync
   - 9 Vertical Sync
 - **Power Consumption**
   - 0.75 Watts from Mac Power Supply
   
# Schematics
The schematics for the board are available [here](/schematics). Additional documentation can be found in the [original eBay listing](https://www.ebay.com/itm/115065111992) or 
in the images directory.

![Power R 2702 Schematics](https://github.com/Stephen-Arsenault/compact-mac-video-output/blob/main/schematics/Power%20R%202702%20Schematics.pdf__LORES.jpg?raw=true)

# BOM
| QTY | ID | Part Description |
| :-------------: | ------------- | ------------- |
| 1  | U1  | 74LS04N |
| 1  | U2  | 74LS14N |
| 1  | U3  | LM340L |
| 1  | R1  | 2K Ω Resistor (4 Watt) |
| 1  | X  | 200 Ω Resistor (4 Watt) |
| 1  | C1  | 25v 10nF Capacitor |
| 1  | C2  | 25v 10uF Capacitor |
| 1  | J1  | 1x5 2.54 Pitch Female Header |
| 1  | X  | Zener Diode |
| 1  | OUT  | Molex 0026481026 ([DigiKey](https://www.digikey.com/en/products/detail/molex/0026481026/26777?s=N4IgTCBcDa4GwBYAcBGADGOACAtgewBsBTADxAF0BfIA)) |
| 1  | IN  | Molex 0009481114 ([DigiKey](https://www.digikey.com/en/products/detail/molex/0009481114/863330?s=N4IgTCBcDaIAwE4AsAOAjBpACAtgewBsBTADxAF0BfIA)) |

# Gerbers
There are two compressed folders in the gerbers directory:
 - `Power R 2702 (Original)`
   - This is a faithful recreation of the original Power R 2702
 - `Power R 2702 (Updated)`
   - This is a simplification of the original board and supports JLC PCB assembly.
   - This version still requires the additional Molex connectors. 

# Special Thanks
A special thanks is owed to the following people:
 - [Zone66x](https://github.com/alxlab-zone66x/) for alerting me to the unique eBay listing where I spent way too much.
 - [Bolle](https://github.com/TheRealBolle) for helping me identify the original Molex connectors.
 - The [Open Retro SCSI Discord server](https://discord.gg/5AtypUqFCT) for being a great place to discuss and brain storm projects. 
