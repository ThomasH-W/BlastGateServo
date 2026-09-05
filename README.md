# BlastGateServo
Blast Gate w/ Servo and ESP32

##Introduction
There are three blast gates in my little toolshop. After the first manual gate failed, I have replaced them with a automatic version.
The housing is a 3D print. It will be moved by a servo mototr. The logic is inside of an ESP32 based on ESPHome.
Example: when the drill press is turned on, the respective blast gate will be opened, all other will be closed and finally the vacuum system will be turned on.
In addition there is a button on each blast gate to request this one to be opened.

## Mechanics

### Housing
The model is based on https://www.printables.com/model/683465-dust-collector-ball-valve-40mm by @Johan_9671. I have updated the knob so it can be turned by 360 degrees to avoid any conflict with the servo movement.

### Servo Mount
I started off the model from @VolkerVolkach : https://www.printables.com/model/1204132-servo-mount-for-blastgates-50mm-ht-tube-servo-halt. My version does not need any print support.

### Cover
I needed a cover to hide the ESP32 and mount a button. In addition it should protect the dust from falling onto the servo.

## Electronics

### Hardware
The Wemos D1 Mini is small enough to be mounted into the cover.
I have added a mosfet in order to control the power for the servo. I just do not want the servo to draw current when not being used.

### Software
My first approach was based on Tasmota but I did not not manage to handle the servos re shutter controls as documented. I switched to ESPHome and it works more reliable.
Anyway the logic is implemented in NodeRED.
