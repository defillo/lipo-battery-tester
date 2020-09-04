License. this project is distributed free for personal use. Yhis means that you can produce your own unit(s) but you are not allowed to make a commercial use of this item
If you want to produce and sell the units, please contact the developer at  defilippi1962@gmail.com


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
Connect to the board with a PC or android device with a serial emulator (for pc, you might need to install ftdi drivers), set baudrate to 57600

Usually the reference voltage value will be 4.500 volt as stated by the Analog Devices datasheet, for what concerns REF194
If you have a very good instrument and you want to deep calibrate the system, check the voltage at pin TP and take note of the value
now multiply by 100 and set as an INT (example: reading is 4.5231, * 100 = 452.31 , set to INT and you get 452)
then send the command V:452 check for the confirm and that's all. 
Firmware defaults to 4.50 if no voltage calibration is issued


using the   TP point with 4.500 V output

Use a short wire and start connecting the 6S pole to this TP
Connect to the board with a PC or android device, set baudrate to 57600

After connecting the 1S wire to the TP, send C:1 <enter> to the board. Calibration of 1S resistor ladder will be stored in flash
proceed with 2S sending C:2, then 3S with C:3 always connecting the relevant pin to TP and so on up to C:6

You will read a reply with the relevant ratio factor in the end. value must be closer to the number of cells
Example. calibrating 4S  will report a factor around 4 and so on


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
defilippis1962@gmail.com


In any case, there will be NO responsability of the author for any damage that may occur under any circumstances to any object that can be related to this project

