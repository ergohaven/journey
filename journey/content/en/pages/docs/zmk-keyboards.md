+++
title = "First steps with a Keyboard on ZMK"
tags = ["guide", "zmk"]
+++

This article provides a guide to help you take your first steps in mastering a keyboard on ZMK. After reading the article, the user will learn how to: manage the keyboard's power, connect the keyboard to multiple devices, and update the firmware.

## Connecting the keyboard

> If you have encountered any issues with connecting keyboard to your device, try to reboot bluetooth on your device and repeat all steps.  

Step 1. First, turn it on by switching the physical toggle to the "On" position.

![image](/images/zmk-keyboards/buttons.png)

Step 2. Next, the halves need to be connected to each other. To do this, simultaneously press the "Reset" button on the bottom of both halves.

Step 3. Once the keyboard is turned on and the halves are connected, you can proceed to connect it to device. First, make sure that the current connection profile is cleared by pressing `&BT_CLR` (in the default layout, the profile control keys are located on layer 3; you can switch to it by holding down the layer 1 and 2 switch keys). This will reset the devices bound to the profile.

![image](/images/zmk-keyboards/sel_clr-en.png)

Step 4. Next, to connect to a device via Bluetooth, you need to press the profile selection key, for example, `&BT_SEL 0`.

Step 5. After pressing, the keyboard will enter pairing mode and appear in the list of available devices for connection. Select it, and voila, everything works!

![image](/images/zmk-keyboards/connect.png)

> **P.S.** If the keyboard is not working correctly, for example, key presses from one half do not reach the device, you should repeat the procedure of connecting the halves by simultaneously pressing the `Reset` key on both.

## Connecting to multiple devices

For wireless connection, the keyboard can remember up to 5 devices. Each connected device is bound to the selected "profile" after connection.  

To connect to the second device, press the `&BT_SEL 1` key, the keyboard will become available for pairing, connect to it from the device.  

To reconnect to the first device, press `&BT_SEL 0`, the device will automatically see the keyboard and connect to it. Similarly, you can connect devices to profiles 3, 4, 5.   

> To unbind the keyboard from your device on the current profile, follow these steps:  
1) clear the profile on the keyboard by pressing `&BT_CLR`, 
2) then unbind the keyboard in the Bluetooth settings on your device,
3) and restart Bluetooth on your device.
After performing these steps, the keyboard should be completely unhooked from your device on the current profile.

![image](/images/zmk-keyboards/sel-en.png)

## Battery status

The current charge of the master (left by default) half is displayed in the OS, in the list of connected Bluetooth devices. Under normal conditions the charge of the secondary half is spent slower than the master half, the exact charge can be seen only with the help of additional software. There are several variants of software for different OS:
- [ZMK Battery Center](https://github.com/kot149/zmk-battery-center) - available on Windows, MacOS;
- [Mighty-Mitts](https://github.com/codyd51/Mighty-Mitts) - available on MacOS;
- [ZMK Split Battery](https://github.com/Maksim-Isakau/zmk-split-battery) - available on Windows;
- [zmkBATx](https://github.com/mh4x0f/zmkBATx) - available on Linux.

![image](/images/zmk-keyboards/power_level.png)

## Turning off the keyboard

You can turn off the keyboard with the [switch on the back of the keyboard](#connecting-the-keyboard) by switching it to the "Off" position, and you can also configure the shutdown directly on the keyboard key by assigning `&SOFT_OFF` to it. When this key is pressed, both halves of the keyboard will be switched to the "Soft off" state. To wake it up, you need to press the `Reset` button on the bottom of the keyboard.

## Entering sleep state

After 10 minutes of inactivity, the keyboard enters sleep mode to save power. To wake it up from sleep, simply press any key, and the keyboard will wake up in a couple of seconds.

## Wired connection

When the keyboard is connected to a device with a USB cable, the keyboard automatically starts transmitting data via the USB cable. After disconnecting the USB cable, the keyboard will return to Bluetooth data transmission mode.

In situations where the keyboard is being charged from one device, but it is necessary to transmit data to another, you can press the `&OUT_BLE` key. This will forcibly switch the keyboard to Bluetooth transmission mode, and data will be sent to the device bound to the current profile.

![image](/images/zmk-keyboards/cables.jpg)

## Keyboard firmware

Updating the keyboard firmware is done as follows:
1) Connect half of the keyboard with a USB cable;
2) Double-click the `Reset` key on the bottom of the keyboard (the pause between clicks should be minimal);
3) Similar to flashing keyboards on QMK, a new removable disk is detected in the PC, and the firmware file must be placed in it;
4) Unplug a USB cable;
5) Reconnect halves by simultaneously pressing the "Reset" button on the bottom of both halves.

**Important!** The firmware of the halves have differences, and the left half must be flashed with a file whose name ends in `left.uf2`, and the right half with a file ending in `right.uf2`. In most cases you can just flash only the master halve (right one for Velvet v3 UI edition, and left for OP36 and Velvet v3) as it stores the keymap. 

> You can switch the keyboard to firmware mode not only by double-clicking `Reset`, but also by pressing the `&bootloader` key. Pressing `&bootloader` switches only the half on which it was pressed to firmware mode.

More information in the ZMK documentation: https://zmk.dev/docs

![image](/images/zmk-keyboards/velvet.jpg)
