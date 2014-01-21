### Raspberry Pi, Raspbmc, boblight and a LightPack


### Prerequisites: 

- Download and install Raspbmc – this must be the July or later release See [http://www.raspbmc.com/download/](#http://www.raspbmc.com/download/) for instructions 
- Download and install this [configuration file](#https://skydrive.live.com/?cid=0f775ea9b6f34329&id=F775EA9B6F34329%211770)
- Install [WinSCP](#http://winscp.net/eng/download.php)
- Install [PuTTy](#http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)
- Follow [this guide](#http://htpcbuild.com/htpc-software/raspberry-pi-raspbmc/connecting-to-raspbmc-ssh/) to establish SSH access for the first time
- Follow [this guide](#http://www.raspbmc.com/wiki/user/root-access/)  to set up root access
Now we can copy the config file

### Operations steps

1. Go into the Raspbmc settings add on under programs
2. Go to System Configuration
3. Scroll down to Service Management
4. Select Boblight Support
5. Connect to your pi using WinSCP, logging in as root and using the IP address you used above.
6. Navigate to /etc
7. Copy the boblight.conf file from above to this location
8. Placing the lights on your TV 
