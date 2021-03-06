![image](http://www.4dsystems.com.au/imagenes/header.png)

ViSi-Genie-RaspPi-Library
====================

4D Systems Raspberry Pi Library for Visi-Genie

Library for the Raspberry Pi to allow easy communication between 4D Intelligent Display modules running ViSi-Genie programmed from Workshop 4, and the Raspberry Pi.

This library is also required for the Raspberry Pi demo programs.

## Genie Pi version 1.2 
=======================================================
*	Added the following function:

	genieWriteStrHex	(int index, long n)
	genieWriteStrDec	(int index, long n)
	genieWriteStrOct	(int index, long n)
	genieWriteStrBin	(int index, long n)
	genieWriteStrBase	(int index, long n, int base)
	genieWriteStrFloat	(int index, float n, int precision)
	
## Genie Pi version 1.1 
=======================================================
*	Added the following function:	
	genieWriteMagicBytes	(int magic_index, unsigned int *byteArray) 
	genieWriteDoubleBytes	(int magic_index, unsigned int *doubleByteArray)
	
* 	Added additional Struct : 
		genieMagicReplyStruct :	cmd, index, length, data[100]	

		
		

## Installation of Genie Pi Library on the Raspberry Pi
=======================================================

  make

  sudo make install

## To Uninstall Genie Pi Library
=================================

  sudo make uninstall
  

## To Install wiringPi library (Required for some applications/demos)
=====================================================================
* Connect your raspberry Pi up to the Internet and download WiringPi library from github:
  
  
  cd
  
  git clone git://git.drogon.net/wiringPi
  
  cd wiringPi
  
  ./build
  
  
* This will then download and install the wiringPi library, assuming you have git installed on your Raspberry Pi already.

* If you encounter an error such as: error while loading shared libraries: libgeniePi.so: cannot open shared object file: No such file or directory
do the following:

  sudo ldconfig -v

This should solve the problem

* Please see here for more detail if you need to install git also (https://projects.drogon.net/raspberry-pi/wiringpi/download-and-install/)
  

## Disable Linux from using the Pi Serial Port so the GeniePi library can instead
=================================================================================
* From terminal, launch leafpad (or your chosen editor) with root:

  sudo leafpad

* Nagivate to /boot/cmdline.txt and remove the following text (LEAVE everything else intact)

  kgdboc=ttyAMA0,115200 console=tty1  
  
* Save the file, overwriting the existing one.
  
* Navigate and edit /etc/inittab
  
* Comment out the bottom line by putting a '#' symbol at the start of it, where the bottom line is:
  
  T0:23:respawn:/sbin/getty -L ttyAMA0 115200 vt100
  
* Save the file, overwriting the existing one
  
* Reboot your Raspberry Pi


## Questions/Issues?

Please sign up for our Forum and ask a question there, or submit a Tech Support Ticket from our website.
http://forum.4dsystems.com.au or http://www.4dsystems.com.au/support
