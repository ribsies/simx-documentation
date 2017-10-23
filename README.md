SimX Setup
===================

This document will explain how to setup everything you would need to run the SimX software with the Sixense hardware.

----------

### Table of contents

[TOC]


Setup Local Server (Demo)
-------------

This will describe how to setup a local server. Usually used for demos that do not have access to reliable internet.

> **Note about Assetbundles**

>When planning on running off a local server, you need to make sure you have the required Assetbundles already cached on the phones and devices that will use the moderator. Since there is no internet connection you will not be able to re-download the Assetbundles. Clearing the cache is disabled while in Demo mode.

### Setup the router

The router should be plugged into power first. It takes a few minutes to boot up. **If you are able**, plug the computer that will be used as the server directly into the router.

### Start the demo server

You need to have the latest server code on your computer. In your terminal, go to the folder where the server is located and run this command

    npm run demo
Wait a few seconds until you see the terminal output something like this

    Server running as Demo
    Ethernet port 192.168.1.22
    Server version 0.3.1
This output will show you the IP address of the computer that is running the server. You will use this later to connect to the server.

**DO NOT CLOSE THE TERMINAL**
The terminal must remain open to keep the server alive.

### Connect the Phones

 1. See this section about setting up the phones and Sixense hardware.  
 2. After setup, make sure the phone is connected to the local router.
 3. Start the **SimX Stage** app.
 4. Sync sixense devices
 5. Once in the menu, click the **Demo** button.
 6. Enter the IP address for the local server and hit enter.
 > The IP address will be saved so the next time you open the app on this device you will not have to input the same IP address.

 7. After you connect to the server you will be taken to the same **Sim Group Selection** screen that is used in the normal version of the app.
 8. Once a **Sim Group** is created it will show up on the list and you will be able to select it.

### Connect the Moderator

1. Start the moderator app on whatever device you are running it on
2. Instead of using the login form, click the button in the bottom left.
3. Enter the IP address for the local server and hit connect.
> This input requires the port as part of the IP address. The port is 3000
> If running the moderator on the same computer as the server you can use http://127.0.0.1:3000

4. You can then select to join a **Sim Group** or create a new one.

----------
Setup Sixense
-------------------

Unpack the Sixense box and lay everything out. And take the controllers and devices out of **shipping mode**.
> **Leaving Shipping Mode:**
> The controllers and head pack need to be connected to a power source to be taken out of shipping mode. This can be a USB to the wall or a computer.
> 
> **Entering Shipping Mode:**
> The device needs to be ON. Hold down the power button, blue light around the power button will turn off **KEEP HOLDING**. After a few more seconds of holding the lights around the power button will flash. After the flash, let go of the button and then tap the button 3 times. The device will now be in shipping mode.

* Plug in the Sixense base and turn it on by pressing the power button on the front. The button will turn blue when its on.

> **Note:**
> Be careful of this button, if the base is turned off while a simulation is running it will mess up the connected devices and might need to be reset. **IF** the power is turned off during a simulation, turn it back on ASAP. Sometimes the devices will reconnect automatically without having to reset the apps.

* Turn on 2 of the hand controllers.

> We only turn on 2 because the bluetooth names are all the same. Only having 2 on at a time makes it easier to connect the right controllers to a phone.

 * Turn on one of the phones and make sure bluetooth is turned on.
 * Connect the 2 hand controllers to the phone via the bluetooth settings.

> **Note:**
> You can get to the bluetooth settings quickly on the phone by swiping down from the tip and long pressing on the bluetooth icon.

* Turn on the headpack and connect it to the Gear VR.

>**Note:**
>The head pack must be attached to the Gear VR before plugging in the phone.

* You can now start the SimX App on the phone, it will tell you to plug it into the Gear VR.
* After plugging it in you need to put it on so the App starts to run. There is a light sensor inside the headset that is used to tell if you have it on or not.
* Once it is fully loaded you will see a notice in game to **Sync the Head Pack**.

> At this point you will notice all the LEDs on the controllers and head pack will be flashing blue.

* To sync the Head Pack you must place it in one of the slots on the base and tap the power button. The blue lights will stop flashing and will turn into a single solid light.
* Do the same thing with the hand controllers. Place each controller in one of the hand controller slots and tap the power buttons. Their lights will do the same.

Everything is now connected and ready to use!

Controls
---
>**Note:**
>The menus on the phone can be used using the joystick to move around and pressing the joystick button to select.
>
>Or you can touch the buttons using the hands. The collider that interacts with menu items is a small sphere located at the tips of the index and middle finger on each hand. This is also how you select buttons on the **Vitals Monitor**

---

>**Sixense Button Map**
> Grab Tool : Hold Trigger
> Sternum Rub : Empty Fist (Hold Trigger without grabbing)
> Check Pulse : Previous Button (Next on Left Hand)
> Abdominal Exam : Next Button (Previous on Left Hand)
> Thumbs Up : Bumper
> Point : A Button

---
>**Moderator Camera Controls**
> Rotate Camera : Left Click + Drag, Touch + Drag
> Zoom In : Scroll Wheel or 2-Finger Pinch
> Pan Camera : Right Click + Drag, 3-Finger + Drag

Help
----
What to do in times of trouble

### Server
The server *should* never turn off and *should* never need to be restarted. Will fill this in when more help issues are discovered.

### Moderator
> **The Moderator is acting strange**
> You can always quickly restart the moderator. The Sim Group will always stay alive as long as someone is inside of it. As long as a phone or another moderator is connected, you can exit and rejoin.

### Phone
> **Battery Life**
> The phones should last ~ 2 hours of constant use. When not in use, the phones will go into sleep mode to conserve energy (We did not used to do this, previously we forced the Gear VR to stay on at all times) So the battery life should be longer than previous.

>**Note:**
>When swapping phones, make sure to completely turn off the Phone no longer being used to make sure the bluetooth devices disconnect completely.

---
> **Heat**
> We have not had any over heating issues for a long time. The battery goes before overheating.

---
> **The Sixense controller/head pack lost its sync**
> You can easily resync the device without exiting the app. Use the same process as mentioned in the setup.

---
> **Hands seem shaky**
> This can happen if it has been running for a while ~45 mins. All you need to do is restart the app and re-sync the devices.
