

# Spotipi Recreation

Spotipi is a project based on the Raspberry Pi Zero, created by Ryan Ward. It displays the album cover of the music playing on Spotify onto a 32x32 LED matrix. 

# Project Journey
 ## Inspiration:

I chose this project because of my strong inclination towards visual learning and hands-on experiences. Despite my limited knowledge of software, hardware, and the Raspberry Pi, I was eager to jump into a project that would contain all three areas while keeping me fully engaged. That's why I chose to create a display that visually represents the album art of the music I'm currently listening to on an LED panel.

Music is a significant part of my creative process and daily routine, so selecting a project that merges visual elements with something as integral as music felt like a natural and exciting choice.

## Research and Planning:

1. Research and Preparation:
- Watched Ryan Ward's video on creating SpotiPi.
- Read Ward's article providing instructions on recreating SpotiPi.
- Purchased the hardware Ward had in his tutorial, which took about a week to arrive.
2. Soldering Concerns:
- Noticed that SpotiPi involved soldering, which I was unsure about.
- Consulted my data science professor, who assured me that I should be able to handle it and offered assistance if needed.
- Watched a YouTube video on soldering Ward had linked in his SpotiPI tutorial.
- Watched a variety of Youtube soldering tutorials.
3. Cost Analysis:
- Examined all the parts and their prices listed in Ward's article.
- Estimated the total cost to be around a hundred dollars, considering it a worthwhile investment.
4. Equipment Acquisition:
- Purchased soldering iron from Hobby Lobby.
- Purchased and borrowed additional equipment due to initially underestimating the requirements.
5. Soldering Practice:
- Obtained faulty circuit board from Family Business.
- Followed soldering tutorials to practice essential skills such as tinning wires, creating solder balls, and attaching wires to solder balls. 
- My father joined me in practicing soldering, and together we elaborated and learned the techniques.

 ### Photos of the Soldering Process
![IMG_7531](https://github.com/d-terrell/Spotipi/assets/168385418/6bb4fc82-0634-4281-948f-2de43a3ab76b)
![IMG_7571](https://github.com/d-terrell/Spotipi/assets/168385418/c3a60790-a5da-4bc6-bcca-ee828fc2c5a3)
## Hardware Assembly
- Soldered GPIO pins 4 and 18 together on the Matrix Bonnet via tinned jumper wire.

- Soldered backside of GPIO pins 4 and 8 on Matrix Bonnet.

- Attached Raspberry Pi Zero and RGB Matrix Bonnet together via GPIO pins

- Attached power cables from the LED Panel power source to the Matrix Bonnet and tighten power cables with a screwdriver.
    - Red to positive.
    - Black to negative.
- Attached ribbon cable from the first end of Matrix Bonnet onto the LED Panel.

- Connected the power supply adapter to the Matrix Bonnet and wall.

### Difficulties:

- Didn't have the right adapters for Raspberry Pi Zero and had to purchase a mini HDMI converter from Walmart.

- Borrowed a USB Female to Micro USB Male Adapter from my data science professor.

- Had to go to the hardware store multiple times because I got the wrong alloy for electrical soldering and needed a 3 mm flat-head screwdriver to loosen and tighten power cables.

- Didn't have jumper wires and couldn't find anywhere in town to purchase them, so they asked for permission to take some from the supply at the college.

- Lack of stabilizers to hold the Matrix bonnet made soldering difficult because the bonnet was uneven.

- Uneven bonnet caused solder to slide into pin holes, making it challenging to remove the solder.

- Failed to remove undesired solder in pin holes.

- Had to redo the connecting wire between pins 4 and 18 multiple times due to difficulty in getting the wire to the solder without messing up the soldered ball on the pins.

- The Raspberry Pi turns off when the Matrix bonnet is attached, so I had to download all the software with the bonnet detached.


## Software Setup
(Note: This setup was completed on a Windows 11 laptop.)

- Downloaded Raspbian OS onto an SD card.

- Installed Git for version control.

- Enabled Windows Subsystem for Linux (WSL) and installed Ubuntu for a Linux environment.

- Enabled virtualization in the system's BIOS settings to support virtual machines.

- Installed Python for programming.

### I kept getting the error:

```
C:\Users\donna\spotipi>bash generate-token.sh
Installing spotipy library:
generate-token.sh: line 2: pip: command not found
generate-token.sh: line 3: $'\r': command not found
Enter your Spotify Client ID:
': not a valid identifier: read: `spotify_client_id
generate-token.sh: line 7: $'\r': command not found
Enter your Spotify Client Secret:
': not a valid identifier: read: `spotify_client_secret
generate-token.sh: line 11: $'\r': command not found
Enter your Spotify Redirect URI:
': not a valid identifier3: read: `spotify_redirect_uri
generate-token.sh: line 15: $'\r': command not found
Enter your spotify username:
': not a valid identifier7: read: `spotify_username
generate-token.sh: line 18: $'\r': command not found
generate-token.sh: line 19: python: command not found
generate-token.sh: line 20: $'\r': command not found
generate-token.sh: line 21: $'echo\r': command not found
###### Spotify Token Created ######
Filename: .cache

```

- Configured the PATH variable to include the necessary paths for Git and Python, allowing easy access from the command prompt:
```
setx PATH "%PATH%;C:\path\to\git\bin;C:\path\to\python;C:\path\to\python\Scripts"

setx PATH "%PATH%;C:\Program Files\Git\bin"
```
## Spotify Developer Application

The Spotify Developer Application is required to link your Spotify account to the Raspberry Pi, enabling it to display the currently playing music from your Spotify account.

- Created a new application within the Spotify developer dashboard.

- Named the application.

- Put in the application description.

- Assigned the redirect irl.

- Recorded the Client ID and Client Secret for future use.

![Screenshot (43)](https://github.com/d-terrell/Spotipi/assets/168385418/c864f733-1daa-4112-9cfc-8ec662933402)












## What is SSH and VNC?
- SSH 
    - Stands for Secure Shell.
    - It's a protocol used for securely connecting to a remote computer or server over a network connection.
    - In this case connecting from windows command prompt to a Raspberry Pi Zero over a network.  

- VNC
    - Stands for Virtual Network Computing.
    - It's a technology that allows you to view and interact with the desktop of a remote computer over a network connection.
    - You can see the remote desktop as if you were sitting in front of it, and you can control it using your mouse and keyboard.




## Hardware
To begin the project, I started out buying the hardware Ryan Ward had linked in his written tutorial of Spotipi:

- [32x32 RGB Led Matrix Panel](https://www.adafruit.com/product/1484)
- [RGB Matrix Bonnet](https://www.adafruit.com/product/3211)
- [Raspberry Pi Zero WH](https://www.adafruit.com/product/3708)
- [Power Supply Adapter](https://www.amazon.com/gp/product/B01N4HYWAM/ref=ppx_yo_dt_b_asin_title_o05_s00?ie=UTF8&psc=1)
- [Micro SD Card Pack](https://www.amazon.com/PNY-Elite-microSDHC-Memory-3-Pack/dp/B07YXJM282/ref=sr_1_18?crid=3GICE52988A25&dchild=1&keywords=micro+sd+card&qid=1609606176&s=electronics&sprefix=micro+%2Celectronics%2C201&sr=1-18)


Later on, I would find out that I would need to obtain or purchase the following hardware/materials:

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



## Raspberry Pi Zero Hardware Assembly

- Attach the standard HDMI cable from the monitor to the mini HDMI converter, then attach the mini HDMI to the mini HDMI output on the Pi Zero. 

- Attach the standard USB cable from the keyboard to the USB Female to the Micro USB Male Adapter. Now plug the Micro USB into the Micro USB Data Port on the Pi Zero. 

- Attach the 2.5A Power Supply from the wall to the Micro USB 5 V Power input on the Pi Zero.

## References

 - [How to Setup a Spotify Cover Art Display with Raspberry Pi](https://www.ryanwardtech.com/guides/how-to-install-spotify-cover-art-display/)

 - [SpotiPi Respiratory](https://github.com/ryanwa18/spotipi)

 - [Beginner how to Solder](https://youtu.be/oqV2xU1fee8?si=tI_ez4oEFrG3muxG)

- [How to Solder a Wire to a Circuit Board](https://youtu.be/y0xDR3St5Gg?si=q9y2QIxO4xkvbMA0)

- [How to Install Raspberry Pi OS on SD Card Mac](https://www.rwardtech.com/guides/how-to-install-raspbian-on-sd-card-mac/)

- [How to Download & Install Git on Windows 11](https://youtu.be/JgOs70Y7jew?si=-cGVdC8P_ayUbq1C)

- [How to install Linux on Windows with WSL](https://learn.microsoft.com/en-us/windows/wsl/install)

- [Windows 11: How To Enable Virtualization (VT-x) in Bios](https://youtu.be/3ZBwFcaed5w?si=CYzdn89738iW8t1V)

