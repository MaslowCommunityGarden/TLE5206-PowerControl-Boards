The circuit boards are electronically the same, one uses thru-hole parts for easier assembly. The thru-hole board uses heat sinks that can be soldered to the board for rigidity.

Many web-based PCB houses will accept an EagleCAD .brd file for manufacturing.

The firmware is a branch of the Maslow Firmware, updated to v1.11 as of 4/10/18. It differs from the master in having a different board ID to allow defining IO pins specific to this board, and using different IO for the AUX pins. Use the Arduino IDE to upload this firmware as you would the master firmware to the stock PowerControl board.

