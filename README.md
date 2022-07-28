The simplest rewritable cartridge for MegaDrive/Genesis with a maximum capacity of 4MB (32Mbit), hardware compatible with the FlashKit MD programmer.

MDFC4MB-github

![MDFC4MB-github](https://user-images.githubusercontent.com/24475390/149984222-c1a1d27c-d783-4d6d-8eb3-69ddee26fa4a.jpg)

My author's PCB design in KiCad format (containing a ready-made compilation in Gerber format for sending to production) is proposed, which allows to manufacture a cartridge for the Sega MegaDrive / Genesis game console, implemented taking into account the minimum need and sufficiency of the circuit design using the MXIC MX29L3211 flash memory chip (structurally, it is also possible to use MX29LV320) in the (P)SOP-44 package.

MDFC4MB-PCB-github

![MDFC4MB-PCB-github](https://user-images.githubusercontent.com/24475390/150021381-3bffb65b-c416-45cf-a307-c182a318816e.jpg)

The project is fully tested for performance. In addition to the memory chip, you will also need an integrated voltage regulator AMS1117 at 3.3V (in a SOT-223 package) to provide regular power to this microcircuit, as well as a shunt capacitor with a rating of 100nF or more according to the documentation (marked "104"). The capacitor is necessary for the stable operation of the cartridge in the set-top box (it is not necessary to work with the programmer). The stabilizer can be replaced with an LED in an smd-case (soldered to the input and output sites of the stabilizer: right and central - with the cathode to the central one). The LED, when switched on in series, provides a stable voltage drop across it (we need to "throw off" about 1.6V) - a nice bonus in this case will be the indication of the "activity" of the cartridge, due to the different current consumption of the memory chip in different modes and, as a result, different brightness and frequency LED flashes (in standby mode, low current - does not glow at all). Please note that LEDs of different colors may have different voltage drops! Orange came up perfectly, but almost all 3V falls on blue - in general, you need to select it. That's it, three "details" are enough! The signal levels of the CMOS memory chips with a three-volt supply and the five-volt TTL circuitry of the set-top box are tolerant of each other (putting resistors in the signal circuits, as suggested by alternative projects, is pointlessly redundant). From a hardware point of view, there are no obstacles to using this cartridge together with the 32X expansion - the speed of modern flash memory chips in read mode should be enough (this is the only possible bottleneck for 32X).

PS. To work with this cartridge (its recording), you need at least an extended version of the FlashKit MD interface management utility: Flashkit MD Plus version 1.0.2.0 or later. [Flashkit MD Plus](https://github.com/MiGeRA/FlashKit-MD-Plus) версии от **[1.0.2.0](https://github.com/MiGeRA/FlashKit-MD-Plus/releases/tag/1.0.2.0)  The recording time of the full volume of the cartridge with the MX29L3211 memory chip is ~150s (according to the datasheet, from 80 to 800s, i.e. we have a good result). Support for working with the MX29LV320 chip is implemented in version **[1.0.3.0](https://github.com/MiGeRA/FlashKit-MD-Plus/releases/tag/1.0.3.0)** - the full recording time is ~ 100 sec, i.e. a little faster (although the record is word-by-word with an "unlock sequence" for each word), it's just that the chip itself is faster (according to the datasheet, it's generally from 24 to 72 seconds), but we don't have an increased programming voltage for it ...

P.P.S. Being fully compatible with the FlashKit MD programmer and the set-top boxes for which it is intended, this cartridge is at least three times cheaper than a functionally similar one offered by krikzz and twice as much as a replica from KY-tech. Taking into account the use of a microcircuit in a "large package" (P)SOP-44, the requirements for soldering skill are minimal. The white lacquer masks the tracing of the tracks, which gives the product a finished look even without the case ;-)

Copyright and Disclaimer
Copyright: MiGeRA (aka Th.K)

This documentation describes Open Hardware and is licensed under the CERN OHL v. 1.2.

You may redistribute and modify this documentation under the terms of the CERN OHL v.1.2. (http://ohwr.org/cernohl). This documentation is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A PARTICULAR PURPOSE. Please see the CERN OHL v.1.2 for applicable conditions
