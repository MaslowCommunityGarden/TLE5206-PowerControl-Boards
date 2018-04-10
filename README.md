# TLE5206 PowerControl Boards

PowerControl board based on the TLE5206. Thru-hole and SMD versions

# About the boards:

The standard Maslow PowerControl board uses a pair of simple surface-mount motor-control chips, the L298P013TR, to control the motors. Each chip can control two motors, up to total 4A divided between the motors. Only three motors are provisioned in the release version of the board. There has been concern about the current capacity of these chips and there have been instances where the chips have been damaged when software malfunctioned. Once a chip is damaged, the board would require replacing a 20-pin surface-mount chip to repair.

The TLE5206 offers higher current capacity, over-temperature and over-current detection and protection, along with a simpler package. In addition, there is a thru-hole version of the chip available that would allow a thru-hole version of the board, easier for some users to construct or repair. While the control pins are different from the L298 chips, the firmware requires very little change to work with the TLE5206.

This is a first stab at using the TLE5206 chips on the PowerControl board.
 -  The Electronics folder has EagleCAD board and schematic files for a SMD version and a thru-hole version. I've built and tested both.
 -  The Firmware folder has a branch of the version 1.11 firmware which implements all the functions of that version as well as a few others I've wished for when working with the standard PowerControl board. It uses a modified board ID arrangement to differentiate it from the standard PowerControl boards and make use of the extended IO pins on the end of the Mega2560. It adds three true PWM pins to the AUX group which might be used for spindle control with some software development. It doesn't implement the software over-current detection that the TLE5206 offers. For now, the chips sense the over-current or over-temperature condition and protect themselves by turning off the outputs.

This design brings:
- separate controller chip for each motor
- higher current capacity (5A) per motor
- thru-hole version to aid hand assembly and repair
- board-mounted heat sinks for the thru-hole version
- mounting holes to match three of the Arduino mounting holes
- AUX pins moved to extended end of board
- 4 digital AUX pins
- 2 analog/digital AUX pins
- 3 PWM-capable digital AUX pins
- board version ID pins avoids using SPI pins

It doesn't bring:
- additional motor control channels
- software over-current or over-temperature sensing

# PCBs
======================

Layout

![Layout](https://raw.githubusercontent.com/MaslowCommunityGarden/TLE5206-Power-Control-Boards/Electronics/PowerDistributionBoardSMDLayout.PNG)

![Layout](https://raw.githubusercontent.com/MaslowCommunityGarden/TLE5206-Power-Control-Boards/Electronics/PowerDistributionBoardThruholeLayout.PNG)

Schematic - SMD version

![Schematic](https://raw.githubusercontent.com/MaslowCommunityGarden/TLE5206-Power-Control-Boards/Electronics/PowerDistributionBoardSMDSchematic.PNG)

Schematic - Thruhole version

![Schematic](https://raw.githubusercontent.com/MaslowCommunityGarden/TLE5206-Power-Control-Boards/Electronics/PowerDistributionBoardThruholeSchematic.PNG)
