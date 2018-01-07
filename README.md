About
-----

Millet is a command line tool for
[Xiaomi Mi Band](https://en.wikipedia.org/wiki/Xiaomi_Mi_Band). It was created
to reverse engineer the protocol but can also be useful for end users. Requires
[BlueZ](http://www.bluez.org) and [expect](http://expect.sourceforge.net).

Usage
-----

First of all you need to find out the Bluetooth MAC address of your band:

    $ sudo hcitool lescan
    LE Scan ...
    88:0F:10:EC:70:22 (unknown)
    88:0F:10:EC:70:22 MI

Then use it to connect:

    $ ./millet 88:0F:10:EC:70:22
    spawn gatttool -I -b 88:0F:10:EC:70:22
    connect
    [88:0F:10:EC:70:22][LE]> connect
    Attempting to connect to 88:0F:10:EC:70:22
    Connection successful
    [88:0F:10:EC:70:22][LE]> char-read-uuid ff01
    handle: 0x0012 	 value: 88 9d 87 b8 00 00 02 8e 00 06 00 02 0e 0a 00 01 
    [88:0F:10:EC:70:22][LE]> Firmware: 1.0.10.14
    char-read-uuid ff0c
    handle: 0x002c 	 value: 33 11 0a 19 11 02 34 0c 00 04 
    [88:0F:10:EC:70:22][LE]> Battery: 51%, 12 cycles, last charge 2017-11-25
    char-read-uuid ff06
    handle: 0x001d 	 value: b7 30 00 00 
    [88:0F:10:EC:70:22][LE]> Steps: 12471
