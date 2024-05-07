# Spotipi Recreation

Spotipi is a project based on the Raspberry Pi Zero, created by Ryan Ward. It displays the album cover of the music playing on Spotify onto a 32x32 LED matrix. 

# Project Journey
 ## Inspiration:

I chose this project because of my strong inclination towards visual learning and hands-on experiences. Despite my limited knowledge of software, hardware, and the Raspberry Pi, I was eager to jump into a project that would contain all three areas while keeping me fully engaged. Music is a significant part of my creative process and daily routine, so selecting a project that merges visual elements with something as integral as music felt like a natural and exciting choice.

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

Raspberry Pi Zero Graphical Datasheet
![PiZerov2](https://github.com/d-terrell/Spotipi/assets/168385418/66c969a1-7fb0-45e0-a7ba-42513faf2901)


## Hardware Assembly
- Soldered GPIO pins 4 and 18 together on the Matrix Bonnet via tinned jumper wire.

- Soldered backside of GPIO pins 4 and 8 on Matrix Bonnet.

- Attached Raspberry Pi Zero and RGB Matrix Bonnet via GPIO pins

- Attached power cables from the LED Panel power source to the Matrix Bonnet and tighten power cables with a screwdriver.
    - Red to positive.
    - Black to negative.
- Attached ribbon cable from the first end of Matrix Bonnet onto the LED Panel.

- Connected the power supply adapter to the Matrix Bonnet and wall.

Photo of Bonnet and Matrix After Assembly 
![IMG_8280](https://github.com/d-terrell/Spotipi/assets/168385418/b0c8fe44-8c1d-4c4a-8d0f-5255b5924abe)

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
    - In this case, connecting from a Windows command prompt to a Raspberry Pi Zero over a network.


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

![IMG_8240](https://github.com/d-terrell/Spotipi/assets/168385418/5751a57e-c3bb-4479-8c68-6c7a1dc7aaed)
![IMG_8242](https://github.com/d-terrell/Spotipi/assets/168385418/ef339c75-d449-4291-85a4-39b43c647e1f)
![IMG_8241](https://github.com/d-terrell/Spotipi/assets/168385418/d9dab790-51a8-4683-bb5c-8459298c926b)


- Exit the configuration tool and reboot your Raspberry Pi Zero to apply the changes:

```
sudo reboot
```
- After the reboot, SSH should be enabled. Verify this by running the following on the Pi's terminal:

```
systemctl status ssh
```
- If SSH is running, you should see that it is active:

![IMG_8246](https://github.com/d-terrell/Spotipi/assets/168385418/49b15f34-fff3-429a-b258-bb8effe85309)

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
My case 1st time:
```
scp .cache donna@192.168.1.30:/home/donna/.cache
```
My case 2nd time:
-r flag with scp to recursively copy the contents of the directory. 
```
scp -r /home/donna/.cache donna@192.168.1.30:/home/donna/

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
My case both times:
```
 mv .cache spotipi/
```
#### Difficulties:
- The first time I attempted this .cache was seen as a file but the second time .cache was seen as a directory and I had to add the flaf -r to recursively copy the contents of the directory to the Pi Zero.

### Run the Installation Script to Complete the Build

1. Install the SpotiPi software on the Pi Zero.
```
 cd spotipi
 sudo bash setup.sh
```

2. Enter the values when prompted:

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


# Current Issues & Possible Solutions 

- Pi zero turns off when the bonnet is attached 
  - It could be a software issue, going to try downloading software for the matrix bonnet and the LED panel.

## First attempt:
I was able to download everything onto the Pi but when it did the reboot process it never turned back on, and I had to start over by reflashing the SD card with a Rasbian OS again. 

    - Overheating / Usage - Most likely because it was hot to the touch and I used it for multiple hours nonstop 
    - Might need a greater power supply?
    - SD Card  - Damage or faulty?

## Second Attempt:
Seemed to run more smoothly & faster the second time when downloading the Rasbian OS. I used the same user and password. I did these commands first before doing anything: 
```
sudo apt update - Updates the package lists for upgrades and new package installation.

sudo apt upgrade - Upgrades installed packages to their latest versions.

sudo apt autoremove - Clean up unnecessary packages and cached package files.
```
After that I ran into this issue when trying to SSH over to the Pi:

```
C:\Users\donna>ssh donna@192.168.1.30
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
The fingerprint for the ED25519 key sent by the remote host is
SHA256:+HcPVbzcgRUh9wZr/m7XGsYyltEZmGninE0YK1GSe5g.
Please contact your system administrator.
Add correct host key in C:\\Users\\donna/.ssh/known_hosts to get rid of this message.
Offending ECDSA key in C:\\Users\\donna/.ssh/known_hosts:3
Host key for 192.168.1.30 has changed and you have requested strict checking.
Host key verification failed.
```
- The SSH key changed because I reflashed the OS
- Needed to remove the old key from the 'known_hosts' file (even though it was the same IP address)

I did this by:
1. Opening the known_hosts file in Notepad.
2. Search for any lines that contain 192.168.1.30 and delete those lines, which was every line, so I deleted everything.
3. Saved the known_hosts file and close the text editor.

4. SSH to Raspberry Pi again and was prompted to accept the new SSH key. 

The next issue was that the .cache file was being read as a directory which was an easy fix but I wonder if the change would affect my outcome

The next issue came when I tried to Install the spotipi software on the Pi using bash setup.sh:

```
donna@raspberrypi:~ $ cd spotipi
donna@raspberrypi:~/spotipi $  sudo bash setup.sh
Ensure packages are installed:
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
libopenjp2-7 is already the newest version (2.5.0-2).
libopenjp2-7 set to manually installed.
python3-dbus is already the newest version (1.3.2-4+b1).
python3-dbus set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
Blacklist soundcard...
Installing spotipy library:
error: externally-managed-environment

× This environment is externally managed
╰─> To install Python packages system-wide, try apt install
    python3-xyz, where xyz is the package you are trying to
    install.

    If you wish to install a non-Debian-packaged Python package,
    create a virtual environment using python3 -m venv path/to/venv.
    Then use path/to/venv/bin/python and path/to/venv/bin/pip. Make
    sure you have python3-full installed.

    For more information visit http://rptl.io/venv

note: If you believe this is a mistake, please contact your Python installation or OS distribution provider. You can override this, at the risk of breaking your Python installation or OS, by passing --break-system-packages.
hint: See PEP 668 for the detailed specification.
Installing pillow library:
error: externally-managed-environment

× This environment is externally managed
╰─> To install Python packages system-wide, try apt install
    python3-xyz, where xyz is the package you are trying to
    install.

    If you wish to install a non-Debian-packaged Python package,
    create a virtual environment using python3 -m venv path/to/venv.
    Then use path/to/venv/bin/python and path/to/venv/bin/pip. Make
    sure you have python3-full installed.

    For more information visit http://rptl.io/venv

note: If you believe this is a mistake, please contact your Python installation or OS distribution provider. You can override this, at the risk of breaking your Python installation or OS, by passing --break-system-packages.
hint: See PEP 668 for the detailed specification.
Installing flask library:
error: externally-managed-environment

× This environment is externally managed
╰─> To install Python packages system-wide, try apt install
    python3-xyz, where xyz is the package you are trying to
    install.

    If you wish to install a non-Debian-packaged Python package,
    create a virtual environment using python3 -m venv path/to/venv.
    Then use path/to/venv/bin/python and path/to/venv/bin/pip. Make
    sure you have python3-full installed.

    For more information visit http://rptl.io/venv

note: If you believe this is a mistake, please contact your Python installation or OS distribution provider. You can override this, at the risk of breaking your Python installation or OS, by passing --break-system-packages.
hint: See PEP 668 for the detailed specification.
Enter your Spotify Client ID:
```
- Good because I was seeing new things like a progress bar and new error messages but bad because I had no idea why they were happening.

- Created a Virtual Environment
    - recommend by the Error messages and chat gpt
    - You create a virtual environment and activate it, you will then be able to install packages inside it
 ```
python3 -m venv venv -  Creates a virtual environment

source venv/bin/activate - Activates the virtual environment

pip install spotipy pillow flask - Installs the required packages

sudo bash setup.sh - Runs the setup script again
```
Kept having issues with Pillow So I did:

```
source venv/bin/activate

pip install pillow
```

setup.sh seemed to be working and then again!! Pillow!!
- legacy-install-failure, meaning there was a problem during the installation of the Pillow package

- My Python version that was installed was 3.11.2
- I decided to find a pillow version that was compatible with python 3.11.2
    - I did this by googling and eventually finding a tutorial on youtube that said what version of pillow I needed, which was PIllow 9.4.0
 ```
 source venv/bin/activate
pip install Pillow==9.4.0
```

Still had the same error  and permission-related errors when using sudo so I recreated the virtual environment, give myself sudo/permissions, and  reinstalled flash and pillow:

```
deactivate  -  Make sure the virtual environment is deactivated
rm -rf venv  - Delete the existing virtual environment directory
python3 -m venv venv  - Recreate the virtual environment
source venv/bin/activate  - Activate the virtual environment

chmod -R 755 venv

pip install Flask
pip install Pillow==9.4.0
```
![IMG_8266](https://github.com/d-terrell/Spotipi/assets/168385418/4f562ac5-69f7-4847-b4b6-8ed8b5241302)

Finally, I ran setup.sh again. Everything seemed to be running smoothly, with no errors, until the terminal stopped at 'collecting pillow ==9.30' and froze. 

The pi was hot to the touch again and I had to unplug and call it a night. 
## References

 - [How to Setup a Spotify Cover Art Display with Raspberry Pi](https://www.ryanwardtech.com/guides/how-to-install-spotify-cover-art-display/)

 - [SpotiPi Respiratory](https://github.com/ryanwa18/spotipi)

 - [Beginner how to Solder](https://youtu.be/oqV2xU1fee8?si=tI_ez4oEFrG3muxG)

- [How to Solder a Wire to a Circuit Board](https://youtu.be/y0xDR3St5Gg?si=q9y2QIxO4xkvbMA0)

- [How to Install Raspberry Pi OS on SD Card Mac](https://www.rwardtech.com/guides/how-to-install-raspbian-on-sd-card-mac/)

- [How to Download & Install Git on Windows 11](https://youtu.be/JgOs70Y7jew?si=-cGVdC8P_ayUbq1C)

- [How to install Linux on Windows with WSL](https://learn.microsoft.com/en-us/windows/wsl/install)

- [Windows 11: How To Enable Virtualization (VT-x) in Bios](https://youtu.be/3ZBwFcaed5w?si=CYzdn89738iW8t1V)



