Documentation, tools and software for the OneTouch VerioIQ blood glucose meter

Bjoern Heller <tec@hellercom.de> (c) 2012

This Software is licensed under GNU/GPL


### Hardware ###

CPU: TI MSP430F2618T, 80-Pin PN Package
Battery: 3.4V 147mAh 0.54Wh LithiumPolymer
Charge/Data: MiniUSB
Display: TFT8K4800FPC-A1-E (LED backlight)
Light: Two front facing warm-white smd-LED's

Comes usually with USB wall-plug-charger.

Pictures here:
http://www.flickr.com/photos/hellercom/sets/72157630442471414/

### Device pinout ###

These pins are accessible through holes in the back of the device.
Beginning from left (TP 97)

1 - Battery (White battery cable) - middle pin
2 - TMS 	(cpu pin 72)
3 - TDI/TCCK	(cpu pin 71)
4 - TDO/TDI	(cpu pin 70)
5 - RST/NMI	(cpu pin 74)
6 - TCK		(cpu pin 73)
7 - ? unknown
8 - VCC/AVCC 	(cpu pin 80)
9 - GND/DV	(cpu pin 52/(53))

### Debugger used ###

MSP-FET430UIF

### Programming ###

The debugger indicates that the security fuse has been blown on the MSP430 cpu.
Fixing this with the "flash-bsl" command and doing a full-erase had no success
while I tried.
I'll try a few things the following days.
It seems, that the cpu already starts its application code before the debugger
can send the erase command.

Debugger output:


pen UIF on /dev/ttyUSB0...
Initializing FET...
FET protocol version is 20409001
Configured for JTAG (2)
Set Vcc: 3000 mV
fet: FET returned error code 4 (Could not find device (or device not supported))
fet: command C IDENT1 failed
fet: identify failed
Trying again...
Initializing FET...
FET protocol version is 20409001
Configured for JTAG (2)
Sending reset...
fet: FET returned error code 30 (Could not access device - security fuse is blown)
warning: fet: reset failed
Set Vcc: 3000 mV
fet: FET returned error code 4 (Could not find device (or device not supported))
fet: command C IDENT1 failed
fet: identify failed

###
