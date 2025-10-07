+++
title = 'Encoder guide'
date = 2025-03-20
author = "Ivan Seleznev"
tags = ["guide"]
+++

![image](/images/encoders/1.png)

First, a little general information about what encoders are.  
The basic principle of their work is that when the user turns the handle of the encoder, a certain key is sent for every n degrees of rotation.  
This is useful in scenarios where you need to press the same key repeatedly, for example, we can assign the volume control function to the encoder, etc. You can turn the encoder in two directions: clockwise and counterclockwise - we can assign an increase in sound volume in one direction, and a decrease in another. With encoders, the volume control becomes very accessible and convenient, and due to the tactile response of the encoder, even a slightly pleasant process.  
In addition to scrolling, encoders can also be pressed, and the function of the press can be absolutely anything, for example, macro or mute.

The only volume control is not the end of the possibilities, but we will talk about that later.

### About hotswap
Recently in keyboards K:03, K:03 Pro and Imperial44 appeared an interesting feature - hotswappable encoders. 
Encoders can be installed in 6 places, 3 in each half of the keyboard, on Imperial44 in one half.  
This is done very simply - we insert the encoder into the socket in the same way as insert switch. 

The places where you can put the encoder differ in the presence of 4 additional round contacts.

![image](/images/encoders/2.png)


When installing encoders, it is important to ensure that the gold plated contacts of the encoder reach the contacts.

![image](/images/encoders/3.png)


The most convenient place is at the bottom of the row, where you have to move your hand the least. However, if you are used to reaching the keys with your index fingers in this position, you can move the encoder to the upper row.

The convenience of hot-swapping an encoder is that you can test it in different positions and choose a suitable one for your needs.

![image](/images/encoders/4.gif)


The encoders are pulled out as easily as they are installed: we take a switch puller, press the latches, and voila, the encoder is pulled out and now you can put standard switch instead

![image](/images/encoders/5.png)


After rearranging the encoders, do not forget to change the configuration of the encoders in Vial, this is done in the Layout tab. We will hide unused encoders, leaving the necessary ones.

![image](/images/encoders/6.gif)


### Examples of use

Some use options are immediately obvious, for example, adjusting the volume or brightness of the screen, but you can come up with really entertaining options, such as the Pomodoro-timer.

#### 1) Adjusting the sound volume
On the actions of the encoder, we assign "Vol +" and "Vol -" from the "App, Media and Mouse" tab. In a combination of encoders, for example, you can assign a complete turn on/off the sound (Mute, the tab App, Media and Mouse), or the microphone is turned off (it requires additional tools, depending on the OS).

![image](/images/encoders/7.gif)


#### 2) Scrolling when using a mouse layer
Some users set up a separate mouse layer in the keyboard, where they assign both the cursor control keys and the mouse keys. This layer can be quite accurate to the tuning of the encoder under the scroll up/down. Moving the encoder - scrolling up/down. And to press the encoder, you can assign a click by the mouse wheel (Mouse 3, the "App, Media and Mouse" tab).

![image](/images/encoders/8.png)

#### 3) Switching between open applications (Alt-Tab)
An interesting option for using an encoder can be the appointment of NEXT Win and Prev Win from the User Vials tab. These keys cling to Alt (OPT on a poppy) + TAB, then they wait a little if the key is pressed again (in case you need to switch not to the last application, but for example after one), and if you are not pressed, the ALT + TAB is released and the application is open.
![image](/images/encoders/9.png)

#### 4) Switching desktops
To switch desktops, use the functions from the Quantum tab: for MacOS bind to the encoder LGUI(KC_LEFT) and LGUI(KC_RIGHT), for Windows LCG(KC_LEFT) and LCG(KC_RIGHT).

![image](/images/encoders/10.png)

#### 5) Screen brightness adjustment
Not very often used, it is convenient to set in one of the additional layers.

![image](/images/encoders/11.gif)

#### 6) Switching browser tabs
Depending on the OS and browser, the hotkey may vary, I use LCS(KC_LBRC) and LCS(KC_RBRC) keys on MacOS in Zen Browser from the Quantum tab.

![image](/images/encoders/12.png)

#### 7) Timer
With the help of an encoder, I've made for myself a certain analog of a physical Pomodoro-timer. Here you can't do without third-party applications, on MacOS the Onigiri Timer is used.
Macro, which opens the application with a timer, and activates the 11th layer on the keyboard, to press the encoder, in the main layer. On the 11th layer, the arrows to the left and right are assigned to the rotation of the encoder, so when the encoder is scrolled, the duration of the installed timer is adjusted. With clicks of an encoder, adjusting the timer time is very pleasant! When the time is displayed, I put it back on the encoder, it turns off the 11th layer and hits enter to run the timer.

In Total, the timer setup looks like this:
1) tap the encoder
2) set the timer duration with an encoder scroll
3) tap the encoder again, and voila, the timer works.

![image](/images/encoders/13.gif)

Of course, a full-fledged productivity timer is still a long way off, but so far I have not found a better solution. 
I hope that one day the guys from Ergohaven will attach an encoder to the Planeta keyboard, improve the firmware, and the keyboard speaker will sing to me about the next past focus session!
### Afterword
I hope that after reading this article the reader has an understanding of what tasks encoders can be used for and what problems they can solve. If you still have doubts about the need for encoders, I recommend you try it, because thanks to a new feature with a hot replacement, the encoder is not nailed to the keyboard. In an extreme case, if the encoder is suddenly everywhere, it can be placed in the part of the keyboard you use the least, leave only a slipper on it, and twist it for the sake of pleasant tactile sensations :)

![image](/images/encoders/14.jpg)

Author: [Ivan Seleznev](https://t.me/Wanyan1337)  
Discuss in our [telegram group](https://t.me/+E-mlq11c97AyZmY6)
