#Lightpack firmware update with Atmel FLIP utility
_Step-by-step tutorial. You can check your Lightpack firmware version in "About" tab of Prismatik_

---

To update firmware you will need following:

* Original [FLIP utility] (http://www.atmel.com/tools/FLIP.aspx) for Atmel microcontrollers
* latest version of Lightpack firmware (.hex file)

##Firmware upload to device
For firmware update on Windows or Linux machine, do the following:

1. Download [latest FLIP version] (http://www.atmel.com/tools/FLIP.aspx) from manufacturer website and install it 
2. Connect your Lightpack to USB and press **"secret"** button (hole on front panel of device, near power socket). You OS will sound you about "new device found". It names **AT90USB162 DFU**
3. Install driver for this new device from ```/Atmel/Flip/usb```
4. Run FLIP. Software interface consists of 3 blocks (see pic. below). All of them are named.
5. In main menu choose **Device→Select**. Choose **AT90USB162** from the list
6. In main menu choose **Settings→Communication→USB**. In the popup window press **Open**. As soon as connection is established, the left interface block (Operations Flow) will become active.
7. Open menu option **File→Load HEX File** . Choose the path (only latin symbols allowed) to the firmware file with **.hex** extension and then the info about it will appear at the central block (FLASH Buffer Information)
8. Make sure that **Erase, Program** and **Verify** are checked and press **Run** button
9. As soon as the firmware is loaded to microcontroller (which has to happen very promptly), click **Start Application** button or simply reconnect Lightpack to USB.

<img src="http://wiki.pixelkit.ru/_ru/images/Tumblr_lgo5u1wS8w1qbbc3b.png">
