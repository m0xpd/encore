# encore!
An Echo/Delay Module for Eurorack, based on the PT2399


<p width=100%, align="center">
<img width=50%, src="https://github.com/m0xpd/encore/assets/3152962/02c193a0-35ad-40d9-97cf-0aa640a7b5b3">
</p>

This repository describes a delay module, developed for electronic synthesisers, in Eurorack format, based on the [Princeton Technology](http://www.princeton.com.tw/en-us/products.aspx) [PT2399](http://www.princeton.com.tw/LinkClick.aspx?fileticket=XG0VYKi9QxE%3d&tabid=341&portalid=0&mid=828&language=en-US) device. 

**Functional Description**

A block diagram of  encore!  is shown below:

<p width=100%, align="center">
<img width=95%, src="https://github.com/m0xpd/encore/assets/3152962/75f8fe05-5f2c-4cbb-b634-e9235c8e7670">
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



**Licensing**

encore! is published under a Creative Commons BY-SA 4.0 [License](https://github.com/m0xpd/encore/blob/main/LICENSE.txt)

**Implementation**

The system is implemented on two PCBs; one for the main electronics and one for the controls and interface components.

The schematic for the main PCB is linked by the graphic below below (click for the full-size schematic):

<p width=100%, align="center">
<img width=75%, src="https://github.com/m0xpd/encore/assets/3152962/1f244f95-ca57-4d0a-877b-78688ec595fc">
</p>  

I should have put a buffer between the PT2399 output filters and the input to the 'output filter' (which doesn't have a very high input impedance), but I 
didn't have any spare op-amp stages. I can live with the loading interactions as they are!

The schematic for the control PCB is linked below:

<p width=100%, align="center">
<img width=75%, src="https://github.com/m0xpd/encore/assets/3152962/e0986f40-e248-4756-a811-1461d0e43b70">
</p>  

The two PCBs are joined electrically and mechanically by the 'Board interface', implemented as two 20-way headers (JP1 and JP2 in the schematics, male on the
 main board and female on the control board). A BoM for the main board is included.

You will find full details of the two printed circuit boards (in files for the Eagle Layout Editor) [here](https://github.com/m0xpd/encore/tree/main/PCBs) and 
a Kicad project defining a front panel [here](https://github.com/m0xpd/encore/tree/main/FrontPanel).

**Specifications**

encore! is 12HP wide and extends 38mm behind the front panel (when a standard Eurorack power header is inserted).

Caution: I've just been reminded (thanks Alex) that the PCBs of the present design overhang the left hand edge of the front panel by approximately 1mm. This 
is **an error on my part**, which I'll correct if ever there's a new 'edition' of encore! Multiple instances of encore! sit next to each other in a rack with 
no worries, but don't try to sit encore! next to a neighbour on its left which doesn't leave sufficient space.

encore! draws 36.5 mA from the +12V rail, 12.5 mA from the -12V rail, and nothing from the 5V rail.

