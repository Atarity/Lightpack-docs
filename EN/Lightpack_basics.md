# Lightpack basics
_This page describes basic work principals of Lightpack._

---
*Table of content:*
  * [Explain me in a few words](#explain-me-in-a-few-words)
  * [And now in detail](#and-now-in-detail)
    * [Software](#software)
    * [Driver](#driver)
    * [Firmware](#firmware)
    * [Master board](#master-board)
    * [LEDs](#leds)
  * [Limitations and further modifications](#limitations-and-further-modifications)
    * [Windows 7 and 8 (Aero interface)](#windows-7-and-8-aero-interface)
    * [Performance](#performance)
    * [OpenGL games support](#opengl-games-support)
    * [DirectX10-11 games support](#directx10-11-games-support)

## Explain me in a few words
Lightpack consists of a master board, additional RGB LEDs, firmware that manages hardware and the image capture software called Prismatik installed in PC. The software figures out an average color of the image displayed on the screen for every capture area corresponded to one LED. After that the color data is transferred by USB to the master board, where the firmware, having handled it, makes the definite LED light by the definite color. This process repeats several dozen times per second.

## And now in detail
Technically Lightpack can be called as a hardware and software system if it wouldn’t sound funny relating to the monitor illumination system. There is everything in it: control software and device driver. Besides that, there are a microcontroller and device firmware. Let’s see everything in detail “top-down”.

### Software
*Prismatik* is available in the [downloads](http://lightpack.tv/downloads). It is installed to the PC and solves two tasks: provides image capture and allows access to the [device settings](https://github.com/Atarity/Lightpack-docs/blob/master/EN/Prismatik_settings_description.md).

The main goal of image capture is to make “a screenshot” of the captured area, to figure out its average color and to transfer the data about it to the device as soon as possible. The number of captured areas is the same as the LED number. So the software must do this operation 10 times per 1 timer count. The number of counts depends on the settings, but there should be not less than 15-20 per second in average. On the page “Mode” of the software settings window this indicator is called “Grab frequency”.

![Prismatik settings](https://lh6.googleusercontent.com/-z5XU1cL2wAE/UMDvgQAQxaI/AAAAAAAAHtM/ZfaknXzrDkA/s800/GUI.png)

Moving capture areas and changing their sizes different effects can be achieved. You may make cross areas –- then the color difference between near LEDs will be not so noticeable. You may make them very narrow – software speed will increase. If you want you may even make a semaphore –- to set the capture area in such a way that when receiving new Skype messages the wall will flash as the icon in system tray. However, to do it, it is better to use [our API](https://github.com/Atarity/Lightpack-docs/blob/master/EN/Prismatik_API.md).

[![Prismatik zones](https://lh6.googleusercontent.com/-noc4VI89mBE/UMDvgTMALuI/AAAAAAAAHuU/DeG8aAEVNOU/s600/255.png)](https://picasaweb.google.com/lh/photo/1Jfc6svsKD0fjZ4pZ117P9MTjNZETYmyPJy0liipFm0?feat=directlink)

The last but not least you should know about Prismatik software is that it is created by means of [Qt framework](http://qt-project.org). It means that the application code is cross platform and it will work in the most popular OS, such as Windows, Linux and OS X.

<iframe width="600" height="344" frameborder="0" src="https://www.youtube.com/embed/tZlb5mIH83A"> </iframe>

So, the software has made a screenshot, calculated an average color and now it should transfer it to the device.

### Driver
Let’s do not pay attention to the way how the data transfer by USB between the program and the device is realized. The standard driver HID that is in every OS takes part in this operation. The driver is installed automatically as soon as you connect Lightpack to your computer for the first time. The system defines it as HID (Human Interface Device). The capture software data is transferred to the device by means of the driver.

### Firmware
Firmware is a microprogram that specifies the microcontroller work –- the basis of Lightpack logic. It is firmware that receives data from PC and on the basis of them PWM signal (Pulse – Width Modulation), which is transferred to the LED hardware drivers. The latest version is available in [Downloads](http://lightpack.tv/downloads). The firmware as well as the software can be modified or updated. In most cases to put the firmware into the microcontroller a programming unit is used, but not in our case. You can upgrade Lightpack firmware by USB by means of [Atmel Flip utility](http://www.atmel.com/tools/FLIP.aspx). The firmware has generated PWM signal to us. What happens to it further?

### Master board
Except microcontroller AT90USB-family of Atmel there are two large micro schemes –- LED drivers –- on the master board. They are responsible for PWM signals decoding and current feed to the LEDs.

[![Lightpack 6.0 board](https://lh5.googleusercontent.com/-xeWJZbsxqvY/TzGII42kFaI/AAAAAAAACfQ/jiC15AAVqfw/s500/IMG_6723.jpg)](https://picasaweb.google.com/lh/photo/1JAh_FyoTmZhZmYnUsf5idMTjNZETYmyPJy0liipFm0?feat=embedwebsite)

There are mini-USB socket and the button that is necessary to switch a microcontroller to the bootloader mode. If you want to assemble Lightpack by yourself, do not forget to read [our recommendations](https://github.com/Atarity/Lightpack-docs/blob/master/EN/Lightpack_DIY.md).

### LEDs
If you ever asked yourself why Lightpack LEDs are separated by the master board, here is the answer: Thanks to module approach we have achieved great flexibility in device installation settings. You may install Lightpack to your netbook and then you will need 4 or even 3 LEDs. You may install Lightpack to your TV with the diagonal 40 inches placing 5 LEDs on each side edge of it. It’s up to you what and how illuminate.

The LEDs used by us consist of 3 semiconductors. Each of them gives its own color: red, green and blue. Changing current we regulate the brightness. Switching on channels in different sequence we get wide color spectrum. For example, mixing 3 colors we get white glow.

![Led positioning](https://lh6.googleusercontent.com/-5xkDCE5ADGE/TjQGD_kajEI/AAAAAAAABsE/CwvvSgVyQ90/s400/OUT_MountSchem.jpg) ![Additive color](https://lh4.googleusercontent.com/_pcbSxfY74TA/TV1EbS6p-SI/AAAAAAAABFc/CAFjx7nSla0/s800/colormodel-rgb.gif)

Planar RGB-LEDs in distinction from through-hole LEDs give a large uniform spot and sufficient brightness. This is brightness margin that gives an opportunity to work on big distances from the wall. At that the light from the near spots mixes, and it gives softer effect when changing the colors.

## Limitations and further modifications
Lightpack is not ideal, of course, despite of our constant modifications and the wish to tune it up. If you have decided to assemble or buy the device, please, read this section at first. The full list of tasks is available on our [tracker](https://github.com/Atarity/Lightpack/issues?sort=created&state=open). You also can register your own issue -– we will definitely regard it.

### Windows 7 and 8 (Aero interface)
When Aero interface in Windows 7 or 8 is switched on, the capture speed 3 times decreases in distinction with Basic interface. The capture and processing are slow enough. The effect is less on the powerful modern machines, but still it is.

Besides that, there is [one more problem](http://code.google.com/p/lightpack/issues/detail?id=185) (russian) with Aero work for the owners of ATI videocards. In this case we are unable.

### Performance
According to Windows task manager the capture software can spend up to 20 % of the CPU and take up to 30 MB of the physical memory. These values vary, of course, in the dependence of the capture settings, area sizes, OS and the power of your PC. We have 1-2% with 35 FPS capture on the test setup (AMD Phenom 2 X6 1090T 3.2GHz + Nvidia GTX 550 Ti @ Win7x64). However, we think we are able to increase the speed by changing capture and color calculation algorithms. We are working on it.

### OpenGL games support
The most of modern games display the graphics to the screen by means of DirectX, or OpenGL which has already become a standard. Starting with the version 4.1.0 the software can capture colors from the most of games for Windows. However, the capture from the games that use OpenGL-render (for example, Quake 3, or Revenge of the Titans) is not available so far. We’re also working in this direction.

### DirectX10-11 games support
It was a new thing for us as well as for our users that there is no predicted capture in the full screen games with API DX10-11 (in DX9 and earlier versions it works). Now to understand the problem more detailed [some](http://code.google.com/p/lightpack/issues/detail?id=142) [tickets](http://code.google.com/p/lightpack/issues/detail?id=133) [from](http://code.google.com/p/lightpack/issues/detail?id=158) our bug tracker can help. Besides that, now **we have the code prototype which capture the picture on these API** and we’re implementing it to our software.
