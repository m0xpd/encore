# encore!
An Echo/Delay Module for Eurorack, based on the PT2399

<p width=100%, align="center">
<img width=75%, src="https://github.com/m0xpd/encore/assets/3152962/a83c3a8b-b351-4c80-ae8b-b005affb1b59">
</p>  
This repository describes a delay module, developed for electronic synthesisers, in Eurorack format, based on the [Princeton Technology](http://www.princeton.com.tw/en-us/products.aspx) [PT2399](http://www.princeton.com.tw/LinkClick.aspx?fileticket=XG0VYKi9QxE%3d&tabid=341&portalid=0&mid=828&language=en-US) device. 

A block diagram of  encore!  is shown below:

<p width=100%, align="center">
<img width=95%, src="https://github.com/m0xpd/encore/assets/3152962/3b00fcf1-232f-4757-ac67-b9971f9ac160">
</p>  

The module uses the PT2399 in an application environment derived from circuits in the [datasheet](http://www.princeton.com.tw/LinkClick.aspx?fileticket=XG0VYKi9QxE%3d&tabid=341&portalid=0&mid=828&language=en-US), but adds resources to enable patching and use in the Eurorack environment. 
These resources are described below.

In addition to the filtering already suggested in the application circuit and supported by the PT2399's integral amplifiers, encore! adds a 2nd order 
input filter and a 4th order output filter in Butterworth configuration. 

Unlike most simple PT2399 delay circuits, which are adjusted by potentiometers, encore! places the key parameters of Delay Length, Repeats (i.e. the gain 
of the recursion/feedback loop) and Level of the 'Wet' signal under voltage control, allowing parameter adjustment by potentiometers and/or CV inputs. 

In the case of the Delay Length, this is achieved by a Voltage Controlled Resistor circuit. 

In the case of the other two parameters, this is achieved by Voltage Controlled Amplifiers.  

Most significantly, encore! allows the user to patch external functions into the feedback/recursion loop that builds the echo (seen in the red dashed box in 
the block diagram above), using a loop send / return feature, which is mixed with the module's internal feedback path. This allows (e.g.) filters to be inserted 
to allow selective echos, multiple delay units to be cross-patched to build up complex echo strutures, etc..

encore! is published under a Creative Commons BY-SA 4.0 [License](https://github.com/m0xpd/encore/blob/main/LICENSE.txt)

The system is implemented on two PCBs - one for the main electronics and one for the controls and interface components.

The schematic for the main PCB is linked by the grachic below below (click for the full-size schematic):
<p width=100%, align="center">
<img width=75%, src="https://github.com/m0xpd/encore/assets/3152962/a8bc0e8a-b121-4ab7-bacd-4c6f2d5c4f6c">
</p>  

The schematic for the control PCB is linked below:
<p width=100%, align="center">
<img width=75%, src="https://github.com/m0xpd/encore/assets/3152962/18645e0d-0a9b-40a5-b186-2d5e4e86c5f5">
</p>  

The two PCBs are joined electrically and mechanically by the 'Board interface', implemented as two 20-way headers (JP1 and JP2 in the schematics, male on the
 main board and female on the control board). A BoM for the main board is included.

You will find full details of the two printed circuit boards (in files for the Eagle Layout Editor) [here](https://github.com/m0xpd/encore/tree/main/PCBs) and 
a Kicad project defining a front panel [here](https://github.com/m0xpd/encore/tree/main/FrontPanel).
