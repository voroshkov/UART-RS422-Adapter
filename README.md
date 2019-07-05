# UART-RS422-Adapter

This is the schematic of UART-RS422 adapter I use to connect Chorus RF Laptimer device to a PC with Cat5 Ethernet cable.

There are 2 slightly different PCBs because pinout of regular Ethernet cable is the same on 2 ends, but I need a crossover schematic:

RJ45 pins 1, 2 Rx <= Tx RJ45 pins 1, 2

RJ46 pins 3, 6 Tx => Rx RJ45 pins 3, 6

## Some explanations

RJ45 pins **1, 2, 3, 6** are used as per [standard wiring](https://en.wikipedia.org/wiki/TIA/EIA-568) for 4-wire 10BASE-T cable. Therefore you'll be able to use any standard Ethernet cable with "straight through" connections mapping.

RS422 full-duplex modules have pins marked **A, B, Y, Z**. When connecting, make sure you choose corresponding inputs and outputs on  modules at both ends:
```
--------- A  <-->  Y ---------
Module 1  B  <-->  Z  Module 2
          Z  <-->  B  
--------- Y  <-->  A ---------

```

Half-duplex modules have only pins marked **A, B**. Connect them as follows:
```
--------- A  <-->  A ---------
Module 1              Module 3
--------- B  <-->  B ---------

--------- A  <-->  A ---------
Module 2              Module 4
--------- B  <-->  B ---------
