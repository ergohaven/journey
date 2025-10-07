---
title: "All about Vial"
tags: ["guide", "vial"]
toc: true
---

Vial is an open-source cross-platform GUI and a QMK fork for configuring your keyboard in real time.

The program let's you customize your keyboard with an easy and intuitive interface without any knowledge about programming.

## First use

- Download and install the latest version of the program or use the web version
- Connect your keyboard and it will be automatically detected
- Unlock the keyboard by clicking on the **Security** menu and then **Unlock**, and follow the instructions that will be displayed on the screen
- Change any key you want and it will be instantly remapped, customize various options to your liking
- Save the layout by clicking **File > Save current layout** (optional)
  
![image](/images/vial/vial01.png)  

*Let's now check what the main tabs do*

## Keymap
As the name suggests, this is where you can view and customize your layout.
Simply click on any key you want to change in the top menu, and then select the key to replace in the bottom menu.
Your new key will be ready to use immediately.

## Layer
Layers allow you to change the functionality of your entire keyboard depending on which **layer** it is currently on. It's best to think of the layers as if they were stacked on top of each other. The keys can be configured to switch between layers as needed, similar to the Shift key on the number row.
You can view each available layer by clicking the corresponding number at the top of the interface. Layer 0 is your base/main layer.

Switching between layers can be done in several ways. From the bottom menu, select the layer tab to view all the different options.

- MO(*) - instantly activates the layer. As soon as you release the key, the layer is deactivated
- DF(*) - changes which layer is the default layer. This remains until you turn off the device
- TG(*) - switches the layer, activating it if it is inactive, and vice versa
- TT(*) - If you hold down the key, the layer is activated, and then deactivated when you release (like MO). If you tap it multiple times, the layer will be turned on or off (eg TG). This requires 5 clicks
- OSL(*) - instantly activates the layer until the next key is pressed
- LT layer (kc) - instantly activates the layer when held down, sends a key code when pressed. The key code can be defined like all other buttons, just select the smaller box inside

### Examples of using layers:

- A separate layer for macros that help you quickly work with incoming mail
- Another layer allows us to open the folders or applications we need in a fraction of seconds
- The next layer is configured for operational work in the browser
- You can place “pieces” of code on a separate layer
- You can also set up a special layer for games


The triangle symbol indicates a gap. This means that the action is the same as the layer below it. This is convenient because keys from different layers can be pressed simultaneously.  

*Now let's look at the bottom menu tabs and check what they do*

- Basic and ISO/JIS are standard ANSI, ISO, JIS keyboard layouts
- Layers - see information about layers above
- Quantum - specific key codes from the QMK firmware, hover over any key code of interest and a description will appear
- Backlight - control RGB backlighting (if your keyboard comes with it) directly from the keyboard
- App, Media and Mouse - additional keys to control applications and media playback, also here you can configure the keyboard to perform mouse actions
- Tap Dance - Set up different actions depending on how the key is used. For example, the same key can be configured to activate a macro when pressed, or activate something else when held (see information below).
- User - here you can find custom keys that we have programmed for your use, just like before, just hover over to find out what each function does
- Macro - macros can be used to perform a pre-programmed sequence of actions (see information below)

## Macros
Macros allow you to send multiple keystrokes when only one key is pressed. They can do whatever you want: type entire sentences, repeat the same actions in games, or even help you program.

### Macros configuration
Open the Macros tab. All macros that can be configured will appear as separate tabs. Select the macro you want to configure.

The next step is to add actions:
- Add action - manually adds an action to the list. Customize it to do exactly what you want. select one of the options - hold, press, release and hold.
- Tap Enter - Many macros end with the **Enter** key, so this button makes adding them easier.
- Record macro - allows you to record a macro directly from the keyboard.


Use these keys to add actions to the list. They will be executed in order when the macro is activated.
Actions can be changed using the arrows on the left.
When you are satisfied with the configuration of all macros, click **Save** to save all changes. If you want to go back to what's already on your device, click **Revert**.

### Examples
- Open the Taskbar on Windows by holding Ctrl+Shift and then pressing Esc:  
![image](/images/vial/vial02.png)  

- Launch the program in Windows by opening the **Start** menu, entering the program name and pressing Enter:   
![image](/images/vial/vial03.png)  

- Entering an address:  
![image](/images/vial/vial04.png)  

###Using Macros
After setting up the macro, you can use it. Simply click on the key you want to use for the macro in your layout, then select it from the bottom menu under the **Macro** tab

![image](/images/vial/vial05.png)  

More information about the Macros feature can be found in the official [QMK documentation](https://docs.qmk.fm/feature_macros)

## Tap Dance
This function allows you to change the assignment of keys depending on how many times you press the key and whether you hold it down.
For example, the **X, C, V** keys can perform **Cut**, **Copy** and **Paste** functions as long as you hold the key down for a short time - no modifiers required.
Or press the semicolon key once, send a semicolon. Press twice, quickly - put a colon.

### Setting up Tap Dance
Click on the Tap Dance tab at the top and one of the available numbers below it.
Each Tap Dance feature can be configured to perform different actions depending on how the button is pressed. In the below case, when the button is **On tap**, the left GUI is pressed, but when the button is On hold, the button activates layer 1. The other two options are **On double tap**. double press) and **On tap + hold** (On tap + hold) can also be configured.

![image](/images/vial/vial06.png)  

Tapping term represents the time during which the firmware distinguishes between actions. If the button is held longer than the press time, it is considered a hold. If the button is held down for less than the duration of the press, it is considered a press.
When you are satisfied with the configuration, click **Save** to save all changes. If you want to go back to what's already on your device, click **Revert**.

### Using Tap Dance
Once the tap dance function is configured and saved, it can be used. Simply click on the key you want to use for tap dance in the keymap and then select it from the bottom menu under the Tap Dance tab

![image](/images/vial/vial07.png)  

More information about the Tap Dance feature can be found in the official [QMK documentation](https://docs.qmk.fm/features/tap_dance)

## Combos
This feature is a chord type solution for adding custom actions. Assign any two keys as one. When two keys are pressed simultaneously (for a certain amount of time), the third one is triggered.

### Combo setup
Click the Combo tab at the top and one of the available numbers below it to display the settings for that specific combination. You can configure up to 4 key combinations to activate one action. Each key must be pressed within the combo's duration. In the example below, pressing the +/= key and the Backspace key will instead cause the Delete key to be pressed

![image](/images/vial/vial08.png)  

### Using Combo
Once the Combo is configured and saved, it can be used. There is no need to assign it to a specific key.

More information about the Combo feature can be found in the official [QMK documentation](https://docs.qmk.fm/features/combo)

## Key overrides
This feature allows you to reassign modifier keys when pressed together with any other key.

### Setting Key Overrides
In the example below, pressing the key combination Left Ctrl + Backspace (two keys to be pressed without any specific time window) will be replaced by Delete

![image](/images/vial/vial09.png)  

### Using key overrides
After setting up the key override function, you can use it immediately. No need to assign to a specific key.

More information about the Key Overrides feature can be found in the official QMK documentation

## QMK Settings
This tab is needed to fine-tune the operation of QMK.

- Magic - swap different modifier keys for convenience
- Grave Escape - This feature allows you to use the Grave key (` and ~) with Escape
- Tap-Hold - fine-tuning the tap hold function
- Auto Shift - press the key with the letter and it will be printed. Press a key and hold it a little longer and you'll get its title version.
- Combo - fine tuning of the combo function
- One Shot Keys - fine-tuning one shot keys
- Mouse Keys - fine-tuning mouse keys

## Matrix Tester
Here you can check the keystrokes on your keyboard.

![image](/images/vial/vial10.png)  
