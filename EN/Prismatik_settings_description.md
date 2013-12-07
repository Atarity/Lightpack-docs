#Description of Prismatik's settings
_This page describes the settings, which are available to the user via the program’s menu options. Due to frequent updates to the capture module, some of these items may not be available in the most recent version of the program. Others may be moved to the profile’s configuration text file or global Prismatik main.conf file. Nevertheless, we try to keep this page up to date._

---
*Table of content:*
  * [Modes](#modes)
  * [Device configurations](#device-configurations)
  * [Profiles](#profiles)
  * [Plugins](#plugins)
  * [Experimental](#experimental)

If you have familiarized yourself with the working principles of the device, many setup questions have probably been answered.

Settings window contains 5 pages (6 if you have enabled advanced GUI). Let us examine them in detail.

##Modes
This page contains a set of settings for different operation modes. These settings apply to the capture or the automatic change of colors and overall application performance.

![Modes page](http://store.pixelkit.ru/img/Prismatik/en-1-mode.jpg)

###Screen Grabbing Mode
In this mode the software analyzes the image on the screen, calculates the colors, and sends them to your device.

###Grab Frequency
This indicates the number of frames that are captured and processed within 1 second. More frames per second increase the quality of the back-lighting effect but also increase the load on the CPU. Frequency of 13-15 frames per second is the lowest comfort threshold for the dynamic scenes.

###Grab Delay
Color reading from the screen occurs as often as milliseconds. This reading interval is controlled by the grab delay setting. The setting is inversely proportional to the frequency of capture. If you want to increase the frequency, reduce capture delay. The optimal range of adjustment is 1 to 93 milliseconds.

###Average color on all LEDs
Checking this box enables computation mode of an average color across all the capture areas. This color is transmitted on all the LEDs. This option allows you to use a comfortable and not distracting backlight for work and movie watching.

###Scene luminosity threshold
It works in two ways: You can adjust Minimum luminosity level for soft and gentle light in the dark scenes or you can adjust Dead-zone luminosity grabbing which ignores small non-black objects on black backgrounds and turning lights OFF in the dark scenes. This is eye-saving vs. eye-killing options which works mutually. We recommend to use threshold for minimum luminosity level.

###Widgets appearance
The group of switches defines capture areas changes. When editing you can drag and drop them, change the size (as if you change the size of windows), change the color by a scroll wheel. The switch “Colored/White” changes the areas lighting. Each capture area has the group of controls that set the color balance for the particular LED or switch it off.

###Mood lamp
In this mode the software provides monochromatic back-lighting regardless of what happens on the screen. Because the capture does not occur, there is almost no load on the CPU. Recommended to designers and to all those that have to strain their eyes for a long time while examining the details of their work in semi-darkness.

###Constant color
The color in this mode is static. The Color button allows you to select the desired illumination color along with the hue, saturation and brightness.

###Change color with rate
The backlight colors in this mode gradually transform. You can also adjust the speed change of color and brightness. Such devices are usually called Mood Lamps.

##Device Configurations
This page contains settings that affect the device.

![Device configurations page](http://store.pixelkit.ru/img/Prismatik/en-2-devices.jpg)

###Overall brightness
Brightness adjustments. It is in on a percentage base and mostly it is set to the maximum.

###Gamma Correction
This setting controls the level of saturation. The available range of adjustment is from 0.00 to 3.00. The effect is clearly detectable in a video.

###Keep lights on after exit
The checked box allows to leave that color which was used by the software before exit from Prismatik. It is useful if you use the device as an illumination lamp.

###Smoothness
This setting controls the degree of smoothness in color transformation. While color depth setting allows you to adjust the amount of shade in the transition between the two colors, this particular setting allows you to adjust the time at which the shades will be displayed. The smoothness setting is turned off when set to 0.

###Number of LEDs
The setting of the capture areas number for the particular device.

In *Prismatik* there are also some settings that are specific for other devices. For example, for *Adalight/Ardulight* a virtual COM-port to which the device is connected is available, the speed of sending data to it and the format of the sending for different firmware and SPI-controlled LED strips as well. For those who don’t have the device itself there is the debugging mode where the final, captured color is displayed on the small widgets in the window on a real time basis.

##Profiles
Starting with version 4.1.0, the software supports profiles, which you can access and configure through the profile page. Each separate profile is written to an .ini file (configuration file) located inside the Prismatik `\Profiles` directory (e.g. `C:\Documents and Settings\Atarity\Prismatik\Profiles`).

![Profiles page](http://store.pixelkit.ru/img/Prismatik/en-3-profiles.jpg)

###Profile
In this section you can create, delete and reset existing profiles. A profile stores all the information from the Modes, Device and Plugins pages as well as program language selection. By changing the size and position of the capture areas, you are changing active profiles. New profile is always created on the basis of the current profile. To reset a profile, use the appropriate button. Also you edit current profile .ini manually in text editor by clicking on "Open in text editor" button.

###Expert mode
This includes an advanced GUI for those that are well familiar with the settings. We do not recommend enabling this feature if you do not plan to read additional documentation.

##Plugins
All current plugins can be downloaded from our repository on GitHub and put to the Prismatik profile directory (see below). Each plugin has its own settings. Be sure to read the tab “Info” to understand the details of its work and setting.

![Plugins page](http://store.pixelkit.ru/img/Prismatik/en-4-plugins.jpg)

###All Plugins
Here you can control all installed plugins that are in the Prismatik profile directory:

`C:\Documents and Settings\Atarity\Prismatik\Plugins` (Windows)
`/Users/<user>/.Prismatik/Plugins` (OS X)
`/home/<user>/.Prismatik/Plugins` (Linux)
each plugin should be placed there within separate directory. Some plugins from the first release work according to their priority, that you can increase or decrease. Only checked plugins actually works.

###Restart Plugins
This button allows you to reset plugins and to install them again from their storage. If you debug or you think that not all plugins have been loaded, press this button.

##Experimental
This page is used by the developers. All the contents are being profiled and you can change them at your own risk. We will not document all the functions of this tab as they are constantly in flux.

###Color balance
The program provides an opportunity to capture an individual brightness adjustment of each channel (RGB) for each individual LED. This is useful if you bought the LEDs that shine unevenly (or wall behind yor monitor is not absolutely white). For example, blue is much brighter than red, etc.


In this case you can adjust each channel brightnes directly from the capturing area. You need to click on the arrow in top-right corner and adjust brightness percentage for channel you need.
