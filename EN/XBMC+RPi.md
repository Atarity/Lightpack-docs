### Raspberry Pi, Raspbmc, boblight and a Lightpack


### Prerequisites: 

- Download and install Raspbmc – this must be the July or later release See [http://www.raspbmc.com/download/](http://www.raspbmc.com/download/) for instructions 
- Download and install this [configuration file](https://skydrive.live.com/?cid=0f775ea9b6f34329&id=F775EA9B6F34329%211770)
- Install [WinSCP](http://winscp.net/eng/download.php)
- Install [PuTTy](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)
- [Establish SSH access](http://htpcbuild.com/htpc-software/raspberry-pi-raspbmc/connecting-to-raspbmc-ssh/)  for the first time
- Set up [root access](http://www.raspbmc.com/wiki/user/root-access/)
Then we can copy the config file

### Operations steps

1. Go to  *Programs* &rarr; *Raspbmc settings* &rarr; *Service management*
2. Select *Boblight support*
3. Connect to your  *RPi* using *WinSCP*, logging in as *root*, and using the IP address you used above
4. Download [the configuration](https://skydrive.live.com/?cid=0f775ea9b6f34329&id=F775EA9B6F34329%211770) and navigate to `/etc`
5. Placing the lights on your TV and set *Boblightd* according to [Instruction](http://ajpawelski.wordpress.com/how-to-raspberry-pi-raspbmc-and-a-lightpack/#part4)

---
Thanks to [Andrew Pawelski](http://apawelski.wordpress.com/). The instruction are based on  [article](http://ajpawelski.wordpress.com/how-to-raspberry-pi-raspbmc-and-a-lightpack/).
