---
Title: "mbeDshield: YET ANOTHER MBED"
Author: "Kazuki Yamamoto(@_K4ZUKI_)"
Abstract:
  THE mbeDshield is YET ANOTHER MBED, which looks like arduino,
  will make you use ANY arduino "shields" from MBEDs
  1768/11U24/11U35. This document is for current PCB design
  version 0.5.0 and future design 0.6.0
...

- 26/Dec/2013 rev1.0
- 30/Dec/2014 rev2.0

# Contents{-}
1. Version history
2. Components
3. Soldering of the Kit
4. Software
5. Schematics of v0.5.0
6. Revision history

# _Version history_
## v0.0.1 = hand-wired prototype
- Sunhayato's universal shield UB-ARD01
- Switch Science(SSCI)'s SSCI-MBED-ETHER-KIT
- mbed 1768

## v0.1.0 = first PCB design as "mbeduino"
- the name already exist but didn't ask to Mr. Google
- old arduino pin-out
- no reset button
- some mistake on reset signal line
- no M3 screw mounting hole but 0.8mm guide hole instead
- USB host supported

## v0.3.7 = second PCB design release
- from this version it is named "mbeDshield", D is large character
- USB host and device supported(mini-B USB on bottom side)
- later arduino pin-out
- A4/A5 pins are multiplexed of analog input or I2C-IO
- no M3 mounting screw hole(FORGOT to add XO)
- no reset switch

## v0.4.0 = third PCB design release
- most of components can be bought from AKIZUKI
- all components on top side
- design bug on Vin capacitor with normal-height(cheap) one (kit uses low height one!)
- M3 mounting hole implemented finally
- silkscreen on Both sides

## v0.4.1 = 4th PCB design rc1
- only data exists
- no RJ45 socket
- 1mm(40mil)line ground
- tail 2x3p pin headers for SPI (p5-8 shared)
- silkscreen on Both sides
- local LDOs on 3V and 5V lines, 0.5A each
- 7-9V input is necessary

## v0.4.2 = 4th PCB design rc2
- only data exists
- split plane ground and Vin
- local LDOs on 3V and 5V lines, 0.5A each
- USB host is powered from mbed on-board LDO
- SMD Vin capacitor
- tail 2x3p high-height pin headers for SPI
- ask SSCI or AKIZUKI for selling??? - maybe after prototype

## v0.5.0 = released 4th PCB design
- sales available from SSCI( https://www.switch-science.com/catalog/1717/ )
- only 1 pcs left(as of 30/Dec/2014) and discontinued
- USB host is available only if main USB is connected(1768 only)
- USB device mode only uses data lines(cannot get power from host)
- I2C is only available with 1768(known bug)

## v0.6.0 = planned 5th PCB design
- only data exists
- local LDO for USB host
- I2C pin-out change: p27/28 → p9/10
- ask SSCI for selling?

# _Components_
| No. | Description                          | AKIZUKI number | 0.1.0 | 0.3.7 | 0.4.0 | 0.4.1 | 0.4.2 | 0.5.0 | 0.6.0 |
|:----|:-------------------------------------|:---------------|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|
| 1   | 2x 20p pin socket                    | C-3138         |   v   |   v   |   v   |   v   |   v   |   v   |   v   |
| 2   | 4x 8p pin socket                     | C-4046         |   v   |   v   |   v   |   v   |   v   |   v   |   v   |
| 3   | 2x 6p pin socket                     | C-4045         |   v   |   v   |   v   |   v   |   v   |   v   |   v   |
| 4   | 2x 10p additional pin socket         | C-7199         |   -   |   v   |   v   |   v   |   v   |   v   |   v   |
| 5   | 2x 6p additional pin socket          | (C-4045)       |   v   |   -   |   -   |   -   |   -   |   -   |   -   |
| 6   | smd USB-A                            |                |   v   |   -   |   -   |   -   |   -   |   -   |   -   |
| 7   | TH USB-A                             | C-160          |   -   |   v   |   v   |   v   |   v   |   v   |   v   |
| 8   | smd USB mini-B                       | C-5843         |   v   |   -   |   -   |   -   |   -   |   -   |   -   |
| 9   | TH USB mini-B                        | C-2235         |   -   |   v   |   v   |   v   |   v   |   v   |   v   |
| 10  | DC jack                              | C-6568         |   -   |   v   |   v   |   v   |   v   |   v   |   v   |
| 11  | 5V SMD LDO                           | I-2503         |   v   |   v   |   v   |   v   |   v   |   v   |   v   |
| 12  | 3.3V SMD LDO                         | I-2502         |   -   |   -   |   -   |   v   |   v   |   v   |   v   |
| 13  | SMD 0.1uF 2012                       | P-355          |   v   |   v   |   v   |   v   |   v   |   v   |   v   |
| 14  | SMD 100ohm                           | R-6101         |   v   |   v   |   v   |   v   |   v   |   v   |   v   |
| 15  | SMD Schottky diode                   | I-2073         |   v   |   v   |   v   |   v   |   v   |   v   |   v   |
| 16  | I2C/Analog switch                    | P-2627         |   v   |   v   |   v   |   v   |   v   |   v   |   v   |
| 17  | TH Vin 100uF/16V                     | P-5002         |   v   |   v   |   v   |   -   |   -   |   v   |   v   |
| 18  | RJ45 Ethernet connector from SSCI    |                |   v   |   v   |       |       |       |       |       |
| 19  | RJ45 Ethernet connector from AKIZUKI | P-4809         |       |       |   v   |       |       |       |       |
| 20  | reset switch                         | P-3647         |       |       |   v   |   v   |   v   |   v   |   v   |
| 21  | SMD Vin 330uF/25V                    | P-6978         |       |       |       |   v   |   v   |       |       |
| 22  | 2x3p high-height pin header          |                |       |       |       |   v   |   v   |   v   |   v   |


# _Soldering of the Kit_
From lower height components:

a. SMD parts C,R,D,LDO
b. mbed socket
c. Vin capacitor
d. USB sockets A and mini-B
e. Vin capacitor
f. DC jack
g. board connectors
  - unplug pins from one of each pair
  - stack with other one
  - solder stacked socket
h. Ethernet RJ45 socket(not for 0.5.0)

# _Software_
#### You can use any existing softwares for mbed. From writer's experience:{-}
- onboard Ethernet + NTP client (mbed1768 + PCB <0.4.0)
- onchip USB host + Bluetooth dongle connected to Wiimote(Wii Rimokon)
 (mbed1768 + PCB <0.4.0)
- 2.8 inch touch LCD shield from Seeed Studio(0.5.0)
- VFD clock shield from SSCI/@hayasita
- Touch Shield(MPR121 used) from sparkfun
- SPI memory LCD from AKIZUKI(need to make your own shield)
    - **breakout board will be available from MARUTSU(2015~)**
- I2C graphic LCD from AKIZUKI(need to make your own shield)
- I2C 16x2 character LCD from AKIZUKI(need to make your own shield)
- Aquestalk Pico from AKIZUKI(need to make your own shield)
- eVY1 shield from SSCI

#### UNDER CONFIRMATIONS:{-}
- Ethernet shield R3 from SSCI/Arduino team
- USB host shield from sparkfun
- Xbee shield from sparkfun
- Gameduino from SSCI

# Schematics of v0.5.0

# Revision history
Revision 1.0: released at C85(2013)

- documented up to 0.4.2

Revision 2.0: released at C87(2014)

- modification/correction/replace from Revision 1.0
- documented up to 0.6.0

| mbeDshield: YET ANOTHER MBED |
|:----------------------------:|
|       Kazuki Yamamoto        |
|          @_K4ZUKI_           |
|         Revision 2.0         |
