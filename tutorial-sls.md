# Recyclables & non-recyclables

## Introduction @showdialog

Micro:bit can be used to test for conductivity of materials by using its pin 0 (1 or 2) and GND (ground) pins. When the material is placed between P0 and GND, a closed circuit (represented by Pin 0 is pressed) indicates it is metallic, while an open circuit (represented by Pin 0 is NOT pressed) indicates it is non-metallic.

This feature allows for exploring and learning about different material properties and enables projects involving conductivity and electrical circuits.

**In this project**
![keychain gif](https://raw.githubusercontent.com/detide/2-recyclable/ee9f72c0505ef0907effdb007b52c149abd6660c/Assets/1-1-keychain%20gif.gif)
* Detect if the material is metal or non-metal 
	- Use Pin 0 and GND 
* Reflect the result on LED screen
	- If the material is metal (conductive), LED shows '✓'.
	- If the material is non-metal (non-conductive), LED shows '✖'.

**Skills learnt**
- [ ] Use of copper tape for conductivity test
- [ ] On pin press function

## Flowchart @showdialog
**Pseudocode explained**

The micro:bit continuously checks the status of pin 0. When an object is placed between Pin 0 and GND, 
- if pin 0 is pressed (indicating a metal object is placed between the conductive tapes), it displays a '✓'icon, 
- else, it displays an '✖' icon. 
Icon is paused on LED screen for 1 second before it is cleared. Then, the code repeats from the beginning.

![flowchart](https://raw.githubusercontent.com/detide/2-recyclable/master/Assets/1-1-flowchart.PNG)

## Part 1
Place the ``||logic:if-then-else||`` block to the ``||basic:forever||`` block.
Set the condition to ``||input:pin [P0] is pressed||``.

```blocks
basic.forever(function () {
    if (input.pinIsPressed(TouchPin.P0)) {
    } else {
    }
})
```
## Part 2
If pin 0 is pressed, show a '✓' icon using ``||basic: show icon '✓'||`` block.

Else, show a '✖' icon using ``||basic: show icon '✖'||`` block.

```blocks
basic.forever(function () {
    if (input.pinIsPressed(TouchPin.P0)) {
        basic.showIcon(IconNames.Yes)
    } else {
        basic.showIcon(IconNames.No)
    }
```

## Part 3
Improve the code by pausing the icons on LED screen for 1 second (``||basic:pause (ms) 1000||`` block) and clearing screen (``||basic:clear screen||`` block) before the code repeats itself.

```blocks
basic.forever(function () {
    if (input.pinIsPressed(TouchPin.P0)) {
        basic.showIcon(IconNames.Yes)
    } else {
        basic.showIcon(IconNames.No)
    }
    basic.pause(1000)
    basic.clearScreen()
})
```

## Download
You can check your code using the simulator on the left.

Once done, ``|Download|`` the program to your micro:bit and test it!

```template
basic.forever(function() {})
```
<script src="https://makecode.com/gh-pages-embed.js"</script><script>makeCodeRender(">{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>