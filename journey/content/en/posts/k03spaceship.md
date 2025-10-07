+++
date = 2025-04-19
title = "K:03 Spaceship Edition: Welcome aboard"
author = "Ivan Seleznev"
tags = ["guide", "K:03"]
+++

![image](/images/k03spaceship/1.jpg)

A couple of months ago, my enormously expanded collection of keyboards was joined by the K:03 Spaceship Edition — a long-awaited split keyboard with a metal case from Ergohaven. In this article, I will share my experience using this "spaceship" and try to describe its features.
Let's get started!

## Case
The keyboard features an anodized aluminum case, which gives the device not only a premium look but also a deep, rich sound to every keystroke.
You can enjoy the keyboard's typing sound in the video [K:03 "Spaceship Edition" preview](https://youtu.be/KwxN4QEYbYo?si=Jye_W-u6q-q23yir).

![image](/images/k03spaceship/2.jpg)
*The K:03 Spaceship Edition adds a concise aesthetic to the workspace (looks great next to a MacBook in Space Gray, as if the devices are from the same line).*

Moreover, the case of the Spaceship Edition is slightly smaller than that of the regular K:03 edition due to a slight reduction in the edges.

![image](/images/k03spaceship/3.jpg)

The height of the K:03 Spaceship Edition, compared to the original K:03, has not undergone noticeable changes.

![image](/images/k03spaceship/4.jpg)

It is worth noting that the Spaceship is much easier to disassemble than in other editions; the back cover is held by 4 bolts that are very easy to unscrew. But on the other hand, why disassemble the keyboard at all if it already noise proofed "out of the box"? Let's move on to sound insulation.

## Noise proofing

![image](/images/k03spaceship/5.gif)

After removing the back cover, we are greeted by a thin plastic sheet, which, as far as I understand, is a screen protecting the keyboard's electrical components from contact with the metal case. I suspect that when assembling the keyboard, it is extremely important not to forget to put this piece back!

![image](/images/k03spaceship/6.jpg)

Under the screen, we see a layer of PE sound proofing material approximately 2 mm thick.

![image](/images/k03spaceship/7.jpg)

After removing the board, we see another PE foam layer about 3.8 mm thick; these two layers ensure the pleasantness of the keystroke sound.

## Form factor
The keyboard has 60 keys — this is a successful format both for those who just starting to dive into the world of ergonomic keyboards, with numbers on the top row, and for already experienced users; if you have recognized the power of the numeric layer, you can assign symbols, F-keys, macros to the top row keys.

![image](/images/k03spaceship/8-en.png)
*Base layer of the [standard K:03 layout](https://journey.ergohaven.xyz/pages/layouts_ru/#k03)*

It's worth noting the possibility of installing hot-swap encoders in the keyboard; you can read more about them in the article [Encoder guide](https://journey.ergohaven.xyz/en-gb/posts/encoders/).

![image](/images/k03spaceship/9.jpg)

## Flexible customization
Over several years of diving in the hobby of split keyboards, I have repeatedly concluded that the coolest thing about split keyboards is their programmability.

The keyboard allows you to set separate processing for a quick tap of each key and for holding down that key.
For example, I currently have it set up so that if you quickly tap the "Spacebar," the operating system will receive a "Spacebar" press, but if you hold it down and don't release it, after about 0.2 seconds, the keyboard will activate the layer where I have all the navigation keys at my fingertips, for example, the keys *"J," "K," "L," and "I"* in this layer have arrows.

![image](/images/k03spaceship/10.png)
*I find this arrangement convenient; Vim users might like the arrow arrangement on H, J, K, L or J, K, L, ;*

Thus, the arrows for navigating text files are always at my fingertips, while essentially not losing any functionality. I haven't yet encountered an application where I needed to hold down the "Spacebar," so I can confidently dedicate it to a layer.

Despite the fact that I called this property of keyboards "programmability," it is not at all necessary to write any code for these settings, because the keyboard can be configured simply by clicking buttons in the Vial graphical interface. More about setting up the keyboard via Vial in the article: [All about Vial](https://journey.ergohaven.xyz/en-gb/pages/docs/vial/)

![image](/images/k03spaceship/11.gif)
*This is how simple reassigning keys looks in Vial*

Here are a few more examples of interesting settings:
1) [RuEn mode](https://journey.ergohaven.xyz/en-gb/pages/docs/ruen/) — a feature that allows you to assign almost any symbol to a key, for example "?", and when you press this key, regardless of which language is selected in the operating system, russian or english, exactly "?" will be typed. It's very convenient, who even came up with the idea of spreading symbols across such different places in different layouts...
2) [Opening a specific application by pressing a key](https://journey.ergohaven.xyz/en-gb/posts/layer_for_apps/)
3) **Home Row Mods** — a popular approach to layout design, which consists of the fact that the home row keys, when held down, will activate the Ctrl, Shift, Alt, or Gui modifiers.

*P.S. Programmability is so addictive that I bothered and found a way to attach it to a regular laptop keyboard using kanata, and now even if I went to a coffee shop with just a laptop, without a keyboard, I can hold down the "C" key, and I will have a Ctrl + C copy combination, magic!*

## OLED screens
There are 2 OLED screens located on the inner edges of the keyboard, which add even more futuristic vibes to the keyboard, it looks like a spaceship control panel.
{{< video
    autoplay="true"
    loop="true"
    muted="true"
    src="/video/k03spaceship/splashscreen.mp4"
>}}
*«Splash Screen» mode*
<br />

Note: The ripple on the screens appears when shooting with a camera — the eye does not see such distortions in real life.

In addition to evoking the atmosphere of conquering space, the screens also carry a functional meaning; you can see various information about the current state of the keyboard on them, such as the active layer and pressed modifiers.

Available screen options:
- **Status (classic)**. Information about the firmware version, the current active layer, Caps Lock status, and Win/Mac mode.
{{< video
    autoplay="true"
    loop="true"
    muted="true"
    src="/video/k03spaceship/classic.mp4"
>}}
*The color indicator also signals the current active layer*
<br />

- **Status (modern)**. Information about the current active layer, the current layout according to [RuEn mode](https://journey.ergohaven.xyz/en-gb/pages/docs/ruen/), held modifiers, and CapsLock, NumLock, ScrollLock status.
{{< video
    autoplay="true"
    loop="true"
    muted="true"
    src="/video/k03spaceship/modern.mp4"
>}}
<br />

- **Bongo Cat**. A funny mode in which a cat slaps with its paws to the rhythm of typing on the keyboard. Anyone will be touched!
{{< video
    autoplay="true"
    loop="true"
    muted="true"
    src="/video/k03spaceship/bongocat.mp4"
>}}
<br />

- **Clock and volume**. Displays the current time and sound volume on the computer. To work, you need to install [qmk-hid-host](https://github.com/danil-tolkachev/qmk-hid-host/releases) on your PC.
{{< video
    autoplay="true"
    loop="true"
    muted="true"
    src="/video/k03spaceship/clockvolume.mp4"
>}}
<br />

## Travel case
The keyboard comes in an excellent quality hard case, let's take a closer look at it.

![image](/images/k03spaceship/17.jpg)

Inside, the case is lined with soft fabric so that the keyboard is more comfortable on long journeys.

![image](/images/k03spaceship/18.jpg)

The halves of the keyboard are fixed with elastic bands, so the keyboard does not dangle around the case during transportation, and does not fall out anywhere when opening the case.

![image](/images/k03spaceship/19.jpg)

The case is zippered, so there's minimal chance of it accidentally opening and the keyboard falling out while I'm searching something in my backpack.

## Summing up
If you are considering the K:03 Spaceship Edition as your first split keyboard, then there is a high chance that you will not want to change this keyboard to another one. Spaceship Edition is a confident step towards keyboards of exceptional quality, keep it up, Ergohaven.

![image](/images/k03spaceship/20.jpg)

Article author: [Ivan Seleznev](https://t.me/Wanyan1337)
Discussion in our [telegram group](https://t.me/+E-mlq11c97AyZmY6)
