# Printed Circuit Boards

This folder contains details of the PCBs required to implement the encore! delay module.

The files are presented in Eagle format.

<p width=100%, align="center">
<img width=95%, src="https://github.com/m0xpd/encore/assets/3152962/c6081ed0-4437-4559-802b-bfd7dc983705">
</p>  

Images of the main board on this repository are currently of a v1 protoype which included an error (a missing resistor), which is corrected in the design files.

## Main Board Capacitors 

The [BoM](https://github.com/m0xpd/encore/blob/main/PCBs/encore%20Main%20Board%20v2%20BoM.txt) is presented in the standard EAGLE format, which is verbose and not always helpful. A description of the capacitors used on the main board is given 
below (refer to the [schematic](https://user-images.githubusercontent.com/3152962/246648781-e0986f40-e248-4756-a811-1461d0e43b70.png) for component idents).

De-coupling capacitors C1, C2, C12, C13, C9, C20, C21 and modulate/de-modulate capacitors for the PT2399, C23, C24, C30, C32 (all having value quoted as 
“0.1u” in the BoM) are disc ceramics with 0.2-inch pitch.

Filter / coupling capacitors (C5, C7, C8, C14, C15, C16, C17, C18, C19, C25, C27, C28, C31, C33) are ceramics (for pF values), or multi-layer ceramics 
(for nF values) with 0.1-inch pitch. Some of these also have value 0.1uF, but they are differentiated from the 0.2-inch pitch parts in the BoM by being quoted 
as having value '100n'.

Polarized capacitors with 0.1-inch pitch are used for power supply smoothing (C3, C4, C10, C11), smoothing the mid-rail voltage of the PT2399 (C22) and 
d.c. blocking (C26, C29).

There is NO C6, due to an indexing error on my part.

