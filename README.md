# encore!
An Echo/Delay Module for Eurorack, based on the PT2399

This repository describes a delay module, developed for electronic synthesisers, in Eurorack format, based on the [Princeton Technology](http://www.princeton.com.tw/en-us/products.aspx) [PT2399](http://www.princeton.com.tw/LinkClick.aspx?fileticket=XG0VYKi9QxE%3d&tabid=341&portalid=0&mid=828&language=en-US) device. 

A block diagram of  encore!  is shown below:

<p width=100%, align="center">
<img width=75%, src="https://github.com/m0xpd/encore/assets/3152962/3b00fcf1-232f-4757-ac67-b9971f9ac160">
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



You will find full details of the two printed circuit boards (in files for the Eagle Layout Editor) here and a Kicad project defining a front panel here.
