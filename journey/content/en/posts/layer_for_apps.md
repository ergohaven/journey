---
date: 2024-07-08
title: "Layer for apps"
author: "Ivan Seleznev"
tags: ["vial"]
---

## Introduction
I’ve been using desktops in Windows for a long time, they’re very useful, I opened a work chat on one desktop, a browser on the second, an IDE on the third, etc., you can quickly switch without taking your hands off the keyboard.

At some point I had 6 active desktops, and to switch from 6 to 1 I had to press the hotkey 6 times... and then back another 6.. The thought arose, maybe there is some kind of hotkey to switch specifically to 6 table? But, unfortunately, there is no such thing in Windows itself, which is strange.

![image](/images/layer_for_apps/1.png)  
*Those same 6 desktops (ノಠ益ಠ)ノ彡┻━┻*

## It's too long; too lazy to read
* Section with a brief summary of the article; for more details, go to the next section.
* Programs pinned to the taskbar can be opened by pressing the combinations GUI + 1-9, if it is already running, the program will expand, cool, but there is a limit on the number. 
* If you need to run more programs, then an excellent solution would be to write scripts on AutoHotKey. With AHK you can assign many different actions to specific keyboard shortcuts. Example scripts can be found in the AutoHotKey section of this article.

## The beginning of a long journey
I found an open source alternative to desktops, the komorebi window manager, tinkered with the application for several days and it didn’t work. It seems to have everything I need, you can set up several tables, there are hotkeys for switching to each and many other interesting features inherent in window managers.

![image](/images/layer_for_apps/2.png)  
*This is the kind of beauty that komorebi allows you to create*  

Didn't work because It seemed inconvenient to configure the tables, there we fill out a json file in which we write which application starts on which table, and this does not work if, for example, I need to open 2 separate profiles of the same browser on different tables, because they have the same .exe file, they start only with different arguments, but unfortunately there was no such tuning in komorebi. Yes, and I only need 6 hotkeys, and the window manager provides a ton of functionality that I don’t really need.

## What are the options for solving the problem?
One day, while surfing YouTube, I came across a video with an interesting layout from Ben Vallack. I especially liked what I heard about combinations with the MEH button (Ctrl + Shift + Alt). It runs on MacOS, as far as I understand there is a Keyboard Maestro program, in it you can assign hotkeys to open any application, and not only.

![image](/images/layer_for_apps/3.png)  
*Keyboard Maestro has a ton of different configuration options for keyboard shortcuts*

If you think about it this way, then I don’t really need desktops, this option would also suit me perfectly, because... Essentially, I just keep 6 applications deployed to full screen on 6 different tables.

Buying a Mac to solve such a problem would be a bit overkill, and in Windows there don’t seem to be any particular problems for me, so I started googling what options there are for implementing such functionality in Windows.

The following options came up:

1. The simplest one and does not require any dancing with tambourines, as it turns out, is already built into Windows, you can pin the program to the taskbar at the bottom and call these programs with the combinations Win + 1-0 (the serial number of the program on the taskbar);

![image](/images/layer_for_apps/4.png)  
*Sleeping cat (and programs pinned to my taskbar)*

2. You can also run scripts using the AutoHotkey program (hereinafter referred to as AHK), in general, this is a good option; in scripts you can make all sorts of logic, like if the application is open, we don’t launch it a second time, but just focus. The method involves immersing yourself in the AHK scripting language, which is a good option, but I decided to google it some more;

![image](/images/layer_for_apps/12.png)  
*Example script on AHK*

3. PowerToys has a “Keyboard Manager” module, it does exactly what is required, using a combination you can open an application, open it with some arguments and other interesting things, which is exactly what I needed, and a couple of other PowerToys modules I'm already in use.

![image](/images/layer_for_apps/5.png)  
*PowerToys Keyboard Manager Window*

## What about the keyboard?
In Vial I decided to make a separate layer for this matter, which I switch to via OSL; it seemed most convenient to me here for several reasons:

    It’s convenient that you don’t have to hold it down, just tap it and it’s already on the layer;
    Unlike TG, OSL activates the layer only for one click and then automatically returns you to the previous layer, which is perfect for my use case, because I can’t imagine a case where I need to switch between applications twice in a row.

I placed the button to activate the layer with applications under my thumb, because I switch between applications very often.

![image](/images/layer_for_apps/6.png)  
*I couldn’t find a good use for OSL for a long time, but here it fits perfectly*

I assigned the functions LGUI(1) - LGUI(0) to the layer itself, to make it easier to remember where which applications were, and scattered hotkeys across the keyboard in such a way that a certain association was created in the head - in the place of the letter T - the hotkey for opening the cart, in the place of the letter W - hotkey for opening the working browser, in place of the letter S is obsidian, in which I take notes (assigned to S, not O because I wanted to place everything under my left hand, it’s convenient so as not to remove my right hand from the mouse/trackball, if someday I get my hands on an HPD with a trackball, and the mouse is no longer so needed, I will probably use the right half for applications).

![image](/images/layer_for_apps/7.png)  

## Let's try the found options
I decided to start with the easiest way to test it - pinning it to the taskbar. First impressions are great, this is exactly what I wanted to get in the end. Due to the fact that I arranged the buttons associatively, I got used to it quite quickly, I make much fewer mouse movements, and the problem that arose with switching from 1 desktop to 6 no longer appears.

I liked the approach so much that the Windows keyboard shortcuts from 1 to 0 weren’t enough, I bound all the most used applications and it wasn’t enough.. Eh

I went to try the second most accessible option for me - already installed PowerToys, in the keyboard manager I tried to reassign the keyboard shortcuts.

![image](/images/layer_for_apps/8.png)  

There is a lot of customization for combinations, in my case I assigned the combination CTRL + ALT + SHIFT (the same MEH from qmk and vial) + A, selected the Action “Run a program” and selected the executable file of the application I needed, vial.

With this approach, everything worked fine, but not with all programs; Steam, for example, for some reason did not work until I selected the option “If running” = “Run another” for it. These are apparently features of specific applications, but it’s worth taking them into account, and by the way, such things did not appear when launching applications from the taskbar, so perhaps it’s worth launching applications like Steam from the task bar.

![image](/images/layer_for_apps/9.png)  
*This is what a layer with bells and whistles from PowerToys looks like*

At this stage, the idea has already been implemented and functions the way I wanted, but I decided to try method 3, scripts with AHK.

AutoHotKey

This required more preliminary steps than in the previous two methods; I installed the AutoHotKey Dash program from the website, using which you can compile the .ahk script into a launchable file.

![image](/images/layer_for_apps/10.png)  
*Program window*

AHK scripts seem to have existed for a very long time, there is a lot of documentation and information on them on the forums. After searching for a while, I came across several examples of how you can implement opening an application using a keyboard shortcut.

```md !+^SC12::  ; E    
{   
    if PID := ProcessExist("Code.exe")
    {
        WinActivate "ahk_pid " PID
    }
    else
    {
        Run "C:\Users\ivans\AppData\Local\Programs\Microsoft VS Code\Code.exe"
    }
    return
}
```

Briefly what is written here:

Line 8: In short, the line indicates that we are doing the key combination Ctrl + Alt + Shift + E. "!+^" is such a designation that the button must be pressed with the modifiers Ctrl + Alt + Shift. “SC12” is a scan code for the E key (I couldn’t figure out why it doesn’t work if I just write a letter instead of the scan code..).

Line 10: here we ask the ProcessExist function whether the desired program is running, in this example Code.exe, if it is running, then we save the process identifier in the PID variable, and go to line 12.

Line 12: Since we have verified that the program is running, we just need to switch to that program's window. We call the WinActivate function and pass it the identifier of the found process, stored in the PID variable.

If on line 10 it turns out that the Code.exe program is not running, then we end up in the else block, on line 16.

Line 16: we found out that the program is not running, we need to run it. Using the Run function, we launch the program, passing the path to the file in quotes.

Next, we compile the script, run the resulting .exe file, and, voila, when you press the key combination, everything magically opens!

In fact, with AHK everything turned out to be much simpler than I initially expected; there really is a lot of documentation, as well as various kinds of answers on the forums. You can find a ready-made script for almost any request.

In most cases, the implemented functionality is not very different from what PowerToys allows you to do, however, there are various non-standard cases when PowerToys can no longer cope, for example, if we run the sample1.exe file, and it runs the sample2.exe file under the hood, and already It is he who hangs in open processes. In this case, AHK allows you to create custom logic: if sample2.exe is not open, then run sample1.exe. Or, for example, it is possible to search for running applications not by the file name, but by the name of the window; this was useful for assigning the opening of the YouTube browser application to a keyboard shortcut.

```md !+^SC1b::  ; Tab    
{   
    if WinExist("YouTube -.*YouTube")
    {
        WinActivate
    }
    else
    {
        Run "C:\Program Files\BraveSoftware\Brave-Browser\Application\chrome_proxy.exe  --args"
    }
    return
}
```

This is a cool thing, it allows you to develop the idea of launching applications in combination to the maximum. I will definitely continue to use it in the future.
Results

In my opinion, it turned out to be 10 out of 10, the number of movements performed by the mouse has decreased very much, and I switch between applications in an instant. Now I’m really ready for HPD with a trackball, before this I had doubts because... I work a lot with the cursor, but with the implemented layer for applications I hardly reach for the mouse. Now we just have to wait for the actual updated HPD.

Another option is to consider implementing such a layer on a macropad, for example, if there are already too many layers on the main keyboard and there is nowhere to cram it.

It is also worth noting that there is literally one situation in which I have not yet found a solution through AHK - how to open two different profiles of the same browser with two different keyboard shortcuts. They seem to have the same process running, and there is no profile name in the window title.. Here I will continue to use opening through the taskbar. And I will most likely give up using PowerToys in the end, because AHK allows you to do the same things, but with more fine-tuning.

## P.S.
If you try to create scripts in AHK, I strongly advise you to read the documentation; you can often find useful examples there. It was a little difficult for me to navigate it and find the specific functions I needed, but it helped that I noticed the sections on the left side of the screen. I found the Process and Window sections most useful for the task of launching applications; they have functions for searching for a running program by any parameters.

![image](/images/layer_for_apps/11.png)  
*https://www.autohotkey.com/docs/v2/lib/ProcessExist.htm*

Author: [Ivan Seleznev](https://t.me/Wanyan1337)  
Discuss in our [telegram group](https://t.me/+E-mlq11c97AyZmY6)
