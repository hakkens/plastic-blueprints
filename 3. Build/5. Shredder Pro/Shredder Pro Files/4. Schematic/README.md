# Auto reverse for Precious Plastic Shredder!

Hi all 🖐,
here we doocument how to enable jam detection and autoreverse for shredder.

More background info about the project can be found here: [Forum topic](https://davehakkens.nl/community/forums/topic/v4-shredder-arduino-code/).

For now we have:

- Arduino code
- Flowchart
- Wiring diagram

## Principle of operation

Use a microncontroller and hall effect sensor to measure motor current consumption and control motor rotation through relays.
It uses a 3 position switch to enable shredding and manual reversing.

## Arduino
Install required libraries:

- LiquidCrystal I2C
- Wire

Both can be installed using Ardunio Library Manager (available from IDE version 1.6.2)
Sketch -> Include Library -> Manage Libraries ...

Load shredderControl/shredderControl.ino to microcontroler

### Params tunning
Running params can be tunned for your particular setup via serial port

Send "config" to enter into configuration mode, current reads will stop waiting for configuration
Send values separated via comas (all are ints)
  
`configV, v0A, startSpan, maxJams, minJamTime, unjamReverseT, maxCurrent`

Default values are:

`0,538,500,3,15000,3000,12`

You can load default values by sending "reset"

> GUI for configuration is being developed

## WIP

Things that are still on the TODO list:

- [ ] Circuit diagram & PCB
- [ x ] Allow configuring parameters from GUI
- [ ] List of components
