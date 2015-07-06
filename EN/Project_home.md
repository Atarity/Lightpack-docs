> We are started this project at the very late of 2010. Since then it covered by open licenses (GPLv3 and CC-BY-SA). In 2013 [we throw Kickstarter campaign](https://www.kickstarter.com/projects/woodenshark/lightpack-ambient-backlight-for-your-displays) and crowdfund $500 000 to run mass-production in China. Year after this moment at May 2014 we were finish to fullfill all our obligations and ship Lightpacks to all our backers. During whole project lifecycle we were produce more than 13k pcs. At May 2014 [the core team leave the project](http://atarity.ru/post/85837330541/after-three-years-we-leave-our-lightpack) and for now it under Woodenshark LLC. You can buy Lightpack thru <http://getlightpack.com> or [DIY](https://github.com/Atarity/Lightpack-docs/blob/master/EN/Lightpack_DIY.md).

Lightpack is a monitor light device used for presence effect strengthening.

<img src="https://lh6.googleusercontent.com/-ZcR-x2kOuQQ/UPAfhlfbilI/AAAAAAAAIU4/UqWdf3dzWhE/s820/tript.jpg" />

<img src="https://lh6.googleusercontent.com/-CPlUv15hE0A/VZpkgVYdiPI/AAAAAAAA7z4/YAO1t8UJLn0/w1024-h654-no/IMG_9665.jpg" />

The software (Prismatik) analyses the image on your monitor and transfers its data by USB to the Ligthpack board. This board lights the surface behind a monitor, TV or laptop by means of RGB LEDs of the corresponded colors. The effect reminds the illumination of Phillips Ambilight TVs most of all.

<a href="http://www.youtube.com/watch?v=1UP7SmUqkxc"><img src="https://lh4.googleusercontent.com/-v3PDpYuOWd4/VZpTqfYTGiI/AAAAAAAA7zk/bzM8UMhS72Y/w854-h511-no/Screenshot_15.png" /></a>

In the project wiki you will find the [operation principal description](https://github.com/Atarity/Lightpack-docs/blob/master/EN/Lightpack_basics.md), the [device assembly instructions](https://github.com/Atarity/Lightpack-docs/blob/master/EN/Lightpack_DIY.md) and the [software description](https://github.com/Atarity/Lightpack-docs/blob/master/EN/Prismatik_settings_description.md). Besides that, [PCB files](https://github.com/Atarity/Lightpack/tree/master/Hardware) in Eagle CAD format, device firmware and software for image capture are stored in [downloads](https://github.com/woodenshark/Lightpack/releases).

**Features:**

- Work with different LEDs number (from 1 to 10) on the diagonals till 36 inches
- Color balance setting for each LED separately
- Individual adjustable capture area for each LED
- Overall average color for all areas calculation mode
- Permanent backlight (lamp) mode
- Capture from video (the most of sources)
- Capture from games (GDI, DirectX)
- Open API for external plugins and scripts
- XBMC integration plugin
- Works with LightFX integrated illumination from Alienware (beta)
- Fast and simple firmware upgrade by USB
- Convenient user profile parameters and hotkeys

**Pecularities:**

- Module structure for installation onto monitors and TVs with different diagonals
- Crossplatform code (Windows, Linux, OS X and even Android)
- Efficient operation on the diagonals from 10 to 50 inches
- Operating distance is from 10 to 35 cm (the distance between LEDs and the surface where the light is projected to)

**Useful URL's:**

- [Prismatik downloads](https://github.com/woodenshark/Lightpack/releases)
- [Lightpack-docs](https://github.com/Atarity/Lightpack-docs) &mdash; this repo. Most complete Lightpack docs here.
- [Lightpack](https://github.com/Atarity/Lightpack) &mdash; source codes of Prismatik, firmware and hardware PCB layouts
- [Lightpack-hardware](https://github.com/Atarity/Lightpack-hardware) &mdash; dedicated R&D repo for hardware 
- [Prismatik-plugins](https://github.com/Atarity/Prismatik-plugins) &mdash; plug-ins repo
- [Photos from DIY early adopters](https://plus.google.com/u/0/photos/108808791782514191974/albums/5578649545433169105)
- [All video updates in YouTube channel](http://www.youtube.com/channel/UCEDih7ao8qLWQMMtvduHCvw)

---------------------
<sup>_* Original [idea](http://habrahabr.ru/blogs/DIY/100085/) and first implementation author is Mike [brunql](https://plus.google.com/104629265144068751816/about) Shatohin._</sup>

<sup>_** We want to save our rights for "Lightpack" name. If you want to produce commercial device which based on our project just mail us._</sup>
