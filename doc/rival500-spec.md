*This file is vastly incomplete. Research is ongoing.*

### Button Configuration Protocol

Out of the box, several of the mouse's buttons are internally deactivated and will not raise any events until they are configured.

When sent by the first-party software, the button configuration packet is 578 bytes long, though only the first 87 bytes seem to be carry information.

The packet starts with the identifier { 0x31, 0x00 }. Following these two bytes, each button's configuartion is layed out in runs of five bytes as follows:

    «c» «a» «?» «?» «?»

    c  = category
    a  = argument

### Button Ordering

The buttons are arranged in this order in the packet:

* Button 1
* Button 2
* Button 3
* Button 4
* Button 5
* Button 6
* Button 7
* Button 9
* Button 10
* Button 11
* Button 12
* Tilt Left
* Tilt Right
* Button 13
* Button 8

**I'm having difficulties finding where the scroll wheel is configured. It does not appear to be in the same packet as the rest of the buttons, and the mouse remembers the setting between systems so its in there somewhere.**

### Categories

    01: Button 1
    02: Button 2
    03: Button 3
    04: Button 4
    05: Button 5
    06: Button 6
    07: Button 7
    08: Button 8
    ...?
    31: Scroll Up
    32: Scroll Down
    33: Tilt Left
    34: Tilt Right
    ...?
    51: Keyboard Character
    ...?
    61: Media Button

#### Keyboard Characters

Alphabetic keys start at 0x04='A' and proceed in order through the alphabet.

#### Media Buttons

e2: Mute
