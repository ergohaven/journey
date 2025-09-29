+++
title = "Velvet v3 – UI Edition"
tags = ["docs", "velvet-ui"]
+++

![image](/images/layouts/velvet-ui.png)

**Velvet v3 - Ultimate Interface Edition** is a keyboard that reduces the need to move your hand to a minimum with a keywell layout and a trackball under your thumb. The curved key placement makes moving your fingers between rows of keys noticeably easier, and the functional trackball, easily accessible under your thumb, nearly eliminates the need to move your hand to the mouse.

## Trackball

![image](/images/velvet-ui/trackball.jpg)

The Velvet UI trackball has one interesting feature - it can detect user touches. In the default layout, briefly touching the trackball will trigger a left mouse button click, and holding your finger on the trackball will activate a special layer with mouse keys.

![image](/images/velvet-ui/layer.png)

On the mouse layer there are other keys for working with the mouse cursor: right mouse button (**MB2**), mouse wheel click (**MB3**), left mouse button click (**MB1**) is duplicated on the layer for convenience, there are also keys for switching to scroll (**&mo 5**) and sniper (**&mo 6**) modes. 
In scroll mode, when you rotate the trackball, instead of moving the cursor, the page scrolls both vertically and horizontally.

{{< video 
    autoplay="true"
    loop="true"
    muted="true"
    src="/video/velvet-ui/scroll.mp4" 
>}}
<br />


Sniper mode reduces the speed of the cursor movement, allowing you to aim it more accurately.

{{< video 
    autoplay="true"
    loop="true"
    muted="true"
    src="/video/velvet-ui/sniper.mp4" 
>}}
<br />

## Trackball touch actions

The action when you touch the trackball is quite flexible, as you can assign any **behavior** to it.

![image](/images/velvet-ui/keymap.png)

By default, the <a href="https://journey.ergohaven.xyz/en-gb/pages/docs/keymap-editor/#custom-behaviors" target="_blank">custom behavior</a> `&cap_sen` is assigned to the trackball touch, briefly touching the trackball produces a left mouse button click, and holding your finger down activates the mouse layer. You can view details of the behavior or change it in the *Behaviors* tab.

![image](/images/velvet-ui/capsen.png)


### Disabling mouse click

To disable the left mouse button click during short-term touch, it is enough to assign `&mo 4` behavior instead of `&cap_sen`. In this way the mouse layer will be activated when touching the trackball, regardless of the duration of the touch.

![image](/images/velvet-ui/keymap-mo.png)

Reassigning trackball touch behavior is also available in **ZMK Studio**.


### Delay turning off the mouse layer

With the assigned behavior `&mo 4` every time you move your finger from one edge of the trackball to the other, the mouse layer is deactivated, and if you move your finger often, for example, with intensive cursor control, there is a chance to press a key, exactly in the interval when the mouse layer is deactivated. Sometimes i wanted to press the left mouse button, but got the *F* key... You can reduce the chance of such a situation by using macros, because in them you can assign a temporary pause between actions.

![image](/images/velvet-ui/senmo.png)

The macro from the screenshot, when the user removes their finger from the trackball, will wait a small delay before disabling the mouse layer, this can help reduce mis-presses.
> With the introduction of a delay before turning off a layer, accidental mouse button clicks may also occur, because there is now a short pause before the layer is turned off. The delay time can be reduced in the macro settings by changing the `Wait (ms)` (default 15 ms) and `Tap (ms)` (default 30 ms) parameters.
 


## Mode switching

Scroll and Sniper modes are activated on the configured layers, by default **5** and **6** respectively, and if you want to use these layers for some other purpose, you can move the activation of these modes to any other layer. See [Scroll Mode Settings](#scroll-mode-settings) and [Sniper Mode Settings](#sniper-mode-settings) on how to change the layer numbers for the modes.
  
In the default layout, modes are switched using the `&mo` behavior, but you can switch modes using any other behavior that activates layers. If you don't want to keep the scroll mode button pressed, you can use the `&tog 5` behavior to activate the mode, then a single tap will activate layer 5 along with the scroll mode, and a second tap will deactivate layer 5 and the scroll mode.

You can also make a hybrid <a href="https://journey.ergohaven.xyz/en-gb/pages/docs/keymap-editor/#custom-behaviors" target="_blank">custom behavior</a> that when held will turn on the layer with the `&mo` behavior, and when tapped will toggle it with the `&tog` behavior.

![image](/images/velvet-ui/mode-behavior.png)

## Trackball configuration

All trackball modes can be customized in the `config/velvet_v3_ui.keymap` file, this can be done quickly and conveniently in the GitHub web-interface by clicking **Edit this file**.

![image](/images/velvet-ui/github-edit.png)

Open the file in your fork and scroll to the very bottom, looking for lines:

```
&trackball { cpi = <1000>; };

&trackball_listener {
    input-processors = <&zip_xy_scaler 9 20>;

    scroller {
        layers = <5>;
        input-processors =
            <&zip_xy_transform INPUT_TRANSFORM_Y_INVERT>,
            <&zip_xy_scaler 1 32>,
            <&zip_xy_to_scroll_mapper>;
    };

    sniper {
        layers = <6>;
        input-processors = <&zip_xy_scaler 1 4>;
    };
};
```

Let's take a look at all the available settings.


### Cursor sensitivity in normal mode

You can change the cursor sensitivity in normal mode in the line `&trackball { cpi = <1000>; };`, the value of `cpi` is set in increments of *200*, and should not be greater than *3200*.

In addition to the `cpi` parameter, a multiplier `<&zip_xy_scaler 9 20>` is also applied, which means that the final sensitivity will be `9 / 20 * cpi`. This value can also be changed.
```
&trackball_listener {
    input-processors = <&zip_xy_scaler 9 20>;
```
You can read more about the available `input-processors` in the ZMK documentation: https://zamk.dev/docs/keymaps/input-processors


### Scroll mode settings

The following settings are available for the scroll mode:
```
scroller {
        layers = <5>;
        input-processors =
            <&zip_xy_transform INPUT_TRANSFORM_Y_INVERT>,
            <&zip_xy_scaler 1 32>,
            <&zip_xy_to_scroll_mapper>;
    };
```
`layers = <5>;` - layers on which the scroll mode will be active. After changing the layer number, you should also change the behavior that switches to the the scroll mode layer.
`<&zip_xy_transform INPUT_TRANSFORM_Y_INVERT>` - scrolling inversion, you can invert both **Y** and **X** axis (`<&zip_xy_transform INPUT_TRANSFORM_X_INVERT>`), or even invert both axes, listing the parameters in commas: `<&zip_xy_transform INPUT_TRANSFORM_Y_INVERT>, <&zip_xy_transform INPUT_TRANSFORM_X_INVERT>,`.
`<&zip_xy_scaler 1 32>` - the scrolling speed is set as a ratio, the default speed is `1 / 32 * cpi`. You can both slow down scrolling by changing the value, for example, to `<&zip_xy_scaler 1 64>`, and speed up scrolling `<&zip_xy_scaler 2 32>`.


### Sniper mode settings

The following settings are available for sniper mode:
```
sniper {
        layers = <6>;
        input-processors = <&zip_xy_scaler 1 4>;
    };
```
`layers = <6>;` - layers on which the sniper mode will be active. After changing the layer number, you should also change the behavior that switches to the the sniper mode layer.
`<&zip_xy_scaler 1 4>` - speed multiplier for sniper mode. By default, in sniper mode the trackball speed is `1 / 4 * cpi`. You can both slow down scrolling by changing the value, for example, to `<&zip_xy_scaler 1 8>`, and speed up cursor `<&zip_xy_scaler 2 4>`.

