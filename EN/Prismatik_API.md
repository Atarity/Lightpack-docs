# Prismatik API description

_This document describes low-level API (documentation is valid for API ver. 1.3), which allows to control the device with the help of external software and plugins via sockets mechanism._

--------------------

_Table of content:_

* [help](#help)
* [exit](#exit)
* [Connection authorization](#connection-authorization)
  * [apikey](#apikey)
* [GET-commands](#get-commands)
  * [getstatus](#getstatus)
  * [getstatusapi](#getstatusapi)
  * [getprofiles](#getprofiles)
  * [getprofile](#getprofile)
  * [getcountled](#getcountled)
* [SET-commands](#set-commands)
  * [lock](#lock)
  * [unlock](#unlock)
  * [setcolor](#setcolor)
  * [setgamma](#setgamma)
  * [setsmooth](#setsmooth)
  * [setbrightness](#setbrightness)
  * [setprofile](#setprofile)
  * [setstatus](#setstatus)

In pactice, you can connect to device from any OS through terminal and send commands to it in real-time. 

<pre>
>> telnet 127.0.0.1 3636
&lt;&lt; Lightpack API v1.3 (type "help" for more info)
</pre>

As a matter of actual practice, it's not very convenient for plugins writing as there's a need of constant control of port sendings and server replies. This is why we created a special wrapper class for Python, which is called pyLightpack. With the help of it you can separate yourself from working on sockets and concentrate directly on plugins. To write controlling scripts with the help of it is easier than to set the config for Quake.) 

However, for the precise understanding of API functionality, we bring forward the full list of interaction commands. From technical point of view this interaction realizes through server, which opens and communicates with the port 3636 (by default). 

## help

<pre>
&lt;&lt; help
</pre>

This command brings the latest information on the current API version and is always available.

## exit

<pre>
>> exit
&lt;&lt; Goodbye!
</pre>

This command closes connection to server and is always available.

## Connection authorization

Starting with ver. 1.1. API supports external connections authorization, which is the most simple way of protection from outside unauthorized connections to device. It supposes sending an authorization key that is only known to server. You always can generate new authorization key or turn authorization off in the settings of Lightpack capturing software. If authorization is on, then the only way to pass through it and gain access to the rest of commands is the command.

## apikey

*Returned values*: *ok or fail*

Sends the authorization key line to the server. If the line matches with the specified in the program, then the server authorizes connection and the user gains access to all API commands. 

<pre>
>> apikey:{209e6248-b0d4-4757-a355-9593ee34f700}
&lt;&lt; fail
>> apikey:IDDQD
&lt;&lt; ok
</pre>

## GET-commands

Available with any connection settings, even if device controlling wasn't passed on to API

## getstatus

*Returned values: on, off, device error or unknown*

Returnes the status of device, which, while being connected to PC, might be turned off (LEDs are not burning) or might be turned on in the capturing software settings. The command returnes device error in case of error of the access to device (the icon in tray changes to the forbidding one). Unknown is a hardly probable event that occurs upon the expiry of request timeout to GUI (~1 s.)  

<pre>
>> getstatus
&lt;&lt; status:on
</pre>

## getstatusapi

*Returned values: idle or busy*

Returnes the current status of API. API is busy if device controlling is realized from outside (by you, your script, by someone from Internet, etc) and is idle if device is being controlled by capturing software. Unless "lock" command is executed (see below) API cannot be busy.

<pre>
>> getstatusapi
&lt;&lt; statusapi:idle
</pre>

## getprofiles

Returnes full profiles list of controlling program settings, separated by ; . Profiles are kept in Profiles folder.
<pre>
>> getprofiles
&lt;&lt; profiles:Lightpack;test07;New profile 1;
</pre>

## getprofile

Returnes the name of the current active profile.
<pre>
>> getprofile
&lt;&lt; profile:test07
</pre>

## getcountleds

Starting with version 5.8 of controlling program, the user got a possibility of controlling various devices with the help of it. For some of them, user can choose by himself the quantity of capturing zones from 1 to 50 according to the quantity of the LEDs in use.

The command returnes the total amount of all capturing zones (active and non-active) in the current profile.

<pre>
>> getcountleds
&lt;&lt; countleds:10
</pre>

## SET-commands

May be executed when device controlling is passed on to API by the "lock" command. 

## lock
*Returned values: success or busy*

Passes on the controlling of device from capturing software to your external script. Unless this command was executed, only GET-commands can be executed by means of API.

<pre>
>> lock
&lt;&lt; lock:success
</pre>

## unlock

*Returned values: success or not locked*

By the analogy with the previous command, passes on the controlling from your script back to Lightpack software. All the settings are applied from the current profile. It is this simple mechanism of priority transfer that makes it possible to use all features of the main capturing program in your scripts to the fullest. 

<pre>
>> unlock
&lt;&lt; unlock:not locked
</pre>

## setcolor

*Syntax: setcolor:N-R,G,B*

*Returned values: ok, error, busy or not locked*

Here and elsewhere in set-commands the reply "busy" means that API is already locked by another script, user via network, etc. (see lock command).

The main command for color setting. N is the number of  LED (same as its capturing zone number). R,G,B - the brightness value of each channel of the pointed LED is set with the value from 0 to 255. Also this commands allows to set colors on some or all LEDs simultaneously. For each of them the construction of N-R,G,B should be separated with ; 

<pre>
>> setcolor:1-0,255,0;5-255,200,30;
&lt;&lt; ok
</pre>

## setgamma

*Syntax: setgamma:N*

*Returned values: ok, error, busy or not locked*

Sets gamma-correction level for the device within the range from 0.01 to 10.00.

<pre>
>> setgamma:2.15
&lt;&lt; ok
</pre>

## setsmooth

*Syntax: setsmooth:N*

*Returned values: ok, error, busy or not locked*

Sets the level of color change smoothness for device within the range from  0 (smoothness disabled) to 255 .

<pre>
>> setsmooth:100
&lt;&lt; ok
</pre>

## setbrightness

*Syntax: setbrightness:N*

*Returned values: ok, error, busy or not locked*

Sets brightness level to all device's LEDs at the same time within the range of 0 (lighting disabled) to 100 .

<pre>
>> setbrightness:80
&lt;&lt; ok
</pre>

## setprofile

*Syntax: setprofile:<name>*

*Returned values: ok, error, busy or not locked*

Turns on the defined settings profile. Profiles list is available on command getprofiles (see above).

<pre>
>> setprofile:My HD video
&lt;&lt; ok
</pre>

## setstatus

*Possible parameters: on or off*

*Returned values: ok, error, busy or not locked*

Turnes the device on or off. Represents the "turn the lighting on/off" button in the software settings.

<pre>
>> setstatus:off
&lt;&lt; ok
</pre>
