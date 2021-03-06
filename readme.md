LightBus
=========

Introduction
------------

LightBus is a **Serial UART** communication protocol made for student robot. The purpose of this protocol is to be lighter than others. It sends 2 bytes with Hardware parity (19 bits). At 57600 baudrate, it took 0.3ms to send a function and a data.

The code is split in 2 parts. One for the master and one for the slaves. This ensure to have a lighter code and more space for our usefull code.

PROS & CONS
-----------

####PROS

* Light (2 bytes, over only ONE wire)
* Cheap (No need for any shield)
* Easy  (Use the common Arduino RX-TX)
* Hardware
* Hardware parity check 
* No crypt, we can plug in & debug (Bluetooth RX/TX module is perfect)
* Opensource
* I2C is open to use it with Servos (dynamixel)

####CONS

* Only ONE master (avoid collisions)
* Only 8 [0:1:7] slaves devices
* Only 16 [0:1:15] functions
* Have to unplug RX/TX before sending the sketch
* NO CRC check (Would take one/two bytes)
* NOT a differential pair (would need a shield)
* NO crypt, we can plug in & hack
* NOT universal
* NO Aknowlegde / Answers (Possible improvement)

CONNEXIONS
-----------

To connect arduinos, you can just connect the TX of the master to every slave's RX. The TX of slaves is unused in this version of LightBus.

**MASTER** *TX*  <=>  *RX* **SLAVE**

PROTOCOL
--------

 * X = adress
 * Y = function
 * D = data

**BYTE 1** : 1XXXYYYY

**BYTE 2** : 0DDDDDDD

|1 adr(3) func(4) | 0 data(7)|

Improvement
-----------

If you want to improve the code, clone it, branch it and contact me : [alexis.paques@gmail.com](mailto:alexis.paques@gmail.com)

LICENSE
-------

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see [http://www.gnu.org/licenses/](http://www.gnu.org/licenses/).


Credits
---------

Alexis Paques
