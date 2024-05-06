

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

## Hardware Purchased:
For the main components, I selected the hardware recommended by Ryan Ward in his detailed tutorial for SpotiPi:

- [32x32 RGB Led Matrix Panel](https://www.adafruit.com/product/1484)
- [RGB Matrix Bonnet](https://www.adafruit.com/product/3211)
- [Raspberry Pi Zero WH](https://www.adafruit.com/product/3708)
- [Power Supply Adapter](https://www.amazon.com/gp/product/B01N4HYWAM/ref=ppx_yo_dt_b_asin_title_o05_s00?ie=UTF8&psc=1)
- [Micro SD Card Pack](https://www.amazon.com/PNY-Elite-microSDHC-Memory-3-Pack/dp/B07YXJM282/ref=sr_1_18?crid=3GICE52988A25&dchild=1&keywords=micro+sd+card&qid=1609606176&s=electronics&sprefix=micro+%2Celectronics%2C201&sr=1-18)
  
As the project progressed, I realized the need to acquire additional hardware and materials, such as a soldering iron, rosin core - Alloy 60SN 40PB, 3mm flat head screwdriver, mini HDMI converter, standard HDMI cable, USB Female to Micro USB Male Adapter, standard USB cable, 2.5A Power Supply, jumper wires, monitor, and keyboard.

## Raspberry Pi Zero Hardware Assembly

- Attach the standard HDMI cable from the monitor to the mini HDMI converter, then attach the mini HDMI to the mini HDMI output on the Pi Zero. 

- Attach the standard USB cable from the keyboard to the USB Female to the Micro USB Male Adapter. Now plug the Micro USB into the Micro USB Data Port on the Pi Zero. 

- Attach the 2.5A Power Supply from the wall to the Micro USB 5 V Power input on the Pi Zero.
  
## Hardware Assembly
- Soldered GPIO pins 4 and 18 together on the Matrix Bonnet via tinned jumper wire.

- Soldered backside of GPIO pins 4 and 8 on Matrix Bonnet.

- Attached Raspberry Pi Zero and RGB Matrix Bonnet via GPIO pins

- Attached power cables from the LED Panel power source to the Matrix Bonnet and tighten power cables with a screwdriver.
    - Red to positive.
    - Black to negative.
- Attached ribbon cable from the first end of Matrix Bonnet onto the LED Panel.

- Connected the power supply adapter to the Matrix Bonnet and wall.

### Difficulties:

- Didn't have the right adapters for Raspberry Pi Zero and had to purchase a mini HDMI converter from Walmart.

- I had to borrow a USB Female to Micro USB Male Adapter from my data science professor.

- I had to go to the hardware store multiple times because I got the wrong alloy for electrical soldering and needed a 3 mm flat-head screwdriver to loosen and tighten power cables.

- Didn't have jumper wires and couldn't find anywhere in town to purchase them, so they asked for permission to take some from the supply at the college.

- Lack of stabilizers to hold the Matrix bonnet made soldering difficult because the bonnet was uneven.

- Uneven bonnet caused the solder to slide into pinholes, making it challenging to remove the solder.

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

## Spotify Developer Application

The Spotify Developer Application is required to link your Spotify account to the Raspberry Pi, enabling it to display the currently playing music from your Spotify account.

- Created a new application within the Spotify developer dashboard.

- Named the application.

- Put in the application description.

- Assigned the redirect irl.

- Recorded the Client ID and Client Secret for future use.

![Screenshot (43)](https://github.com/d-terrell/Spotipi/assets/168385418/c864f733-1daa-4112-9cfc-8ec662933402)


## Installing SpotiPi Software

### Generate Spotify Authentication File
(Note: This was completed on a Windows 11 laptop.)

- Copied Ryan Ward's SpotiPi repository on the cmd prompt.
```
git clone  https://github.com/ryanwa18/spotipi.git
```
-  Changed into the directory that the git clone created, SpotiPI
```
 cd spotipi
```
- Ran the generate token script and entered the prompted Spotify credentials: Client ID, Client Secret, Redirect URI, Spotify Username. 
```
 bash generate-token.sh
 ```

The authentication token has been created in the form of a file named .cache

 
![Screenshot (29)](https://github.com/d-terrell/Spotipi/assets/168385418/cb144ddb-c1bb-4057-8863-cb1c9f19da2a)


 #### Difficulties:

I kept getting the following error when trying to run the bash script, generate-token.sh :

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
Error Solution:
- Python and Git were accessible in Windows PowerShell but not in the Command Prompt, so I needed to update their paths for the command prompt. 
- Configured the PATH variable to include the necessary paths for Git and Python, allowing easy access from the command prompt:
```
setx PATH "%PATH%;C:\Python3.12.3\Scripts"

setx PATH "%PATH%;C:\Program Files\Git\bin"
``` 
I was still receiving the same error message:
-  Multiple installations of the Bash executable were installed which confused the system.
-  Since I'm using Git Bash, I need to use the Bash executable from the Git installation directory.

-  Ran bash script using the full path to the Git Bash executable:
 ```
  C:\Program Files\Git\bin\bash.exe" generate-token.sh
  ```
### SSH to Raspberry Pi 


Before copying the authentication file to the Raspberry Pi and running the installation script on the Pi, I needed to SSH to the PI.
- SSH

    - Stands for Secure Shell.
    - It's a protocol used for securely connecting to a remote     computer or server over a network connection.
    - In this case connecting from windows command prompt to a Raspberry Pi Zero over a network.


1. Type the following command on the PI Zero terminal to get the IP address of the network being used to link the Pi and computer:
``` 
hostname -I
```
- My IP address was: 192.168.1.30

2. Enable SSH on Pi Zero:

- Run the following command to open the Raspberry Pi Configuration tool:
```
sudo raspi-config
```
- In the configuration tool, navigate to Interfacing Options and then select SSH. Choose Enable and then select OK.

-- insert photos here --

- Exit the configuration tool and reboot your Raspberry Pi Zero to apply the changes:

```
sudo reboot
```
- After the reboot, SSH should be enabled. Verify this by running the following on the Pi's terminal:

```
systemctl status ssh
```
- If SSH is running, you should see that it is active:

-- insert photo of SSH status --

3. Connect to Pi from the Computer via SSH:

- On the computer type in the cmd prompt:
```
ssh pi@your_pi_zero_ip
```
- In my case, it was:

```
ssh donna@192.168.1.30
```

- After entering the command, you will be prompted to enter the password for the Pi user. Note that when you type the password, it may not show characters on the screen. Trust that you have typed it correctly and press Enter. If successful, you will see the following message:

![Screenshot (34)](https://github.com/d-terrell/Spotipi/assets/168385418/8dabce8a-11b2-4f59-aab0-8c8af35c1a79)


#### Difficulties:

- I had to change my location from school to home because a firewall was blocking my SSH access to the Raspberry Pi.


### Copy the Authentication File to Raspberry Pi

1.  scp .cache file over to the Raspberry Pi
- scp - Stands for "secure copy."
- It is a command-line utility that allows you to securely copy files and directories between two locations over a network.
```
$ scp .cache-<username> pi@spotipy.local:/home/pi
```
My case:
```
scp .cache donna@spotipy.192.168.1.30:/home/donna/.cache
```

2. Cloned the SpotiPi repository to the Pi Zero
```
git clone https://github.com/ryanwa18/spotipi.git
```

### Move the Authentication File to the Proper Directory on Raspberry Pi
Moved the .cache file from its current location to the root directory of the cloned repository.

```
 mv <path_to_cache_file> <path_to_cloned_repository>
```
My case:
```
 mv /home/donna/.cache /home/donna/myrepo/.cache
```

### Run the Installation Script to Complete the Build

1. Installed the SpotiPi software on the Pi Zero.
```
 cd spotipi
 sudo bash setup.sh
```

2. Entered the values when prompted:

- Spotify Client ID: the token created on the Spotify developer dashboard

- Spotify Client Secret: the secret token created on the Spotify developer dashboard

- Spotify username: the username for your Spotify account

- Spotify Redirect URI: the redirect URI set within the Spotify developer dashboard

- Full path to your Spotify token: the path to where you stored the Spotify authentication file on your Raspberry Pi. 

### Edit Settings on the Web App to Match the Hardware 

- Opened the web browser and navigated to the following link:

```
http://<raspberrypi_hostname or ip_address>
```

My case:

```
http://192.168.1.30
```

Within the web interface, you can perform the following actions:

- Turn the display on or off.
- Adjust the brightness of the display.
- Adjust the size of the display.
- Adjust the refresh rate of the display in hertz (Hz).

![Screenshot (42)](https://github.com/d-terrell/Spotipi/assets/168385418/31182fbd-1207-4311-8447-e4797539954d)





## References

 - [How to Setup a Spotify Cover Art Display with Raspberry Pi](https://www.ryanwardtech.com/guides/how-to-install-spotify-cover-art-display/)

 - [SpotiPi Respiratory](https://github.com/ryanwa18/spotipi)

 - [Beginner how to Solder](https://youtu.be/oqV2xU1fee8?si=tI_ez4oEFrG3muxG)

- [How to Solder a Wire to a Circuit Board](https://youtu.be/y0xDR3St5Gg?si=q9y2QIxO4xkvbMA0)

- [How to Install Raspberry Pi OS on SD Card Mac](https://www.rwardtech.com/guides/how-to-install-raspbian-on-sd-card-mac/)

- [How to Download & Install Git on Windows 11](https://youtu.be/JgOs70Y7jew?si=-cGVdC8P_ayUbq1C)

- [How to install Linux on Windows with WSL](https://learn.microsoft.com/en-us/windows/wsl/install)

- [Windows 11: How To Enable Virtualization (VT-x) in Bios](https://youtu.be/3ZBwFcaed5w?si=CYzdn89738iW8t1V)

