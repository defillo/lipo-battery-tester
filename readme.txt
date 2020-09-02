Assemly is not difficult. care must be taken in welding MCU and FTDI chip
For MCU, use hotair if available

Programming:

Use devicessuch as PICKIT4 or PICKIT3
Use MPLABX IPE v.5.40 or newer

Need 4 pins for programming Vpp,GND,PGD,PGDC, board as a small 4way, 1 mm pitch connector. dot is Vpp
Please take care that the 1S connector has no key. inserting battery probe reversed causes permanent damage at leat to the MCU so be careful

FTProg is used to program the FTDI chip with the String descriptor you like.
device vendor and ID are the standard ones, do not change them otherwise the Android app will not open automatically 

Calibration:
theres a TP point with 4.500 V output

Use a short wire and start connecting the 6S pole to this TP
Connect to the board with a PC or android device, set baudrate to 19200

After connecting the 6S wire to the TP, send C6 <enter> to the board. Calibration of 6S resistor ladder will be stored in flash
proceed with 5S sending C5, then 4S with C4 always connecting the relevant pin to TP

Calibration is stored in the MCU flash so no need to do it again unless you flash the board again
That case is better to preserve EEPROM area in MPLABX IPE

APP

The app will immediately show the 
1)total Voltage
2 the charge percentage (based on 4.20 = 100% , 3.3V = 0%)
3)the different cells voltages
4) The mean value of the cells
5) The percentage of charge of each cells
6) The deviation of the voltage of the cell on respect of the mean value. shown in millivolts

If you prefere to have the board already mounted and running, please ask by mail to
assistenza@androidefillo.it

