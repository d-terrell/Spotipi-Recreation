
# Spotipi Recreation

Spotipi is a project based on the Raspberry Pi Zero, created by Ryan Ward. It displays the album cover of the music playing on Spotify onto a 32x32 LED matrix. This project is intded for myself for learning purposes.I selected this project to gain a broad knowledge of both software and hardware. Although it has been challenging, it has been a great learning experience.
## Hardware
To begin the project I started out buying the hardware Ryan Ward had linked in his written out tutorial of Spotipi:

- [32x32 RGB Led Matrix Panel](https://www.adafruit.com/product/1484)
- [RGB Matrix Bonnet](https://www.adafruit.com/product/3211)
- [Raspberry Pi Zero WH](https://www.adafruit.com/product/3708)
- [Power Supply Adapter](https://www.amazon.com/gp/product/B01N4HYWAM/ref=ppx_yo_dt_b_asin_title_o05_s00?ie=UTF8&psc=1)
- [Micro SD Card Pack](https://www.amazon.com/PNY-Elite-microSDHC-Memory-3-Pack/dp/B07YXJM282/ref=sr_1_18?crid=3GICE52988A25&dchild=1&keywords=micro+sd+card&qid=1609606176&s=electronics&sprefix=micro+%2Celectronics%2C201&sr=1-18)


Later on I would find out that I would need to obtain or purchase the following hardware/materials:

- Soldering Iron
- Rosin Core - Alloy 60SN 40PB
- 3mm Flat Head Screwdriver
- Mini HDMI convertor
- Standard HDMI cable
- USB Female to Micro USB Male Adapter
- Standard USB cable 
- 2.5A Power Supply
- Jumper Wires
- Monitor
- Keyboard


## Spotpi Hardware Assembly

- Solder GPIO pins 4 and 18 together on the Matrix Bonnet via tinned jumper wire.

- Solder backside of GPIO pins 4 and 8 on Matrix Bonnet.

- Attach Raspberry Pi Zero and RGB Matrix Bonnet together via GPIO pins.

- Attach power cables from LED Pannel power source to Matrix Bonnet and tightened power cables with a screwdriver.
  - Red to positive.
  - Black to negative. 

- Attach ribbion cable from first end of Matrix Bonnet on to the LED Pannel.

- Connect power supply adapter into the Matrix Bonnet and wall.
### Photos of the Soldering Process
![IMG_7531](https://github.com/d-terrell/Spotipi/assets/168385418/6bb4fc82-0634-4281-948f-2de43a3ab76b)
![IMG_7571](https://github.com/d-terrell/Spotipi/assets/168385418/c3a60790-a5da-4bc6-bcca-ee828fc2c5a3)

### Photos of Fully Assembled Hardware

## Raspberry Pi Zero Hardware Assembly

- Attach standard HDMI cable from monitor to mini HDMI convertor then attach the mini HDMI to the mini HDMI output on the Pi Zero. 

- Attach standard USB cable from keyboard to USB Female to Micro USB Male Adapter. Then plug the Micro USB to the Micro USB Data Port on the Pi Zero. 

- Attach 2.5A Power Supply from wall to Micro USB 5 V Power input on the Pi Zero.

## References

 - [How to Setup a Spotify Cover Art Display with Raspberry Pi](https://www.ryanwardtech.com/guides/how-to-install-spotify-cover-art-display/)

 - [SpotiPi Respiratory](https://github.com/ryanwa18/spotipi)

 - [Beginner how to Solder](https://youtu.be/oqV2xU1fee8?si=tI_ez4oEFrG3muxG)

- [How to Solder a Wire to a Circuit Board](https://youtu.be/y0xDR3St5Gg?si=q9y2QIxO4xkvbMA0)

- [How to Install Raspberry Pi OS on SD Card Mac](https://www.rwardtech.com/guides/how-to-install-raspbian-on-sd-card-mac/)

- [How to Download & Install Git on Windows 11](https://youtu.be/JgOs70Y7jew?si=-cGVdC8P_ayUbq1C)


- [How to install Linux on Windows with WSL](https://learn.microsoft.com/en-us/windows/wsl/install)

- [Windows 11: How To Enable Virtualization (VT-x) in Bios](https://youtu.be/3ZBwFcaed5w?si=CYzdn89738iW8t1V)
