# Electric Vehicle Prototype
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
solar=github:climate-action-kits/pxt-fwd-edu
```
## Step 1 @showdialog
Plug your USB cable into the micro:bit and insert it into the 
Climate Action Kit board. Click on the button to the right of 
download and follow the steps to pair your micro:bit.
![Plug your USB cable into the micro:bit and insert it into the 
Climate Action Kit board. Click on the button to the right of 
download and follow the steps to pair your micro:bit.](https://raw.githubusercontent.com/mbakhtar/iste-electric-vehicle-v1/master/pair%20microbit-280x203.gif)

## Step 2 
Click on the ``||fwdMotors:Motors||`` drawer and drag the
``||fwdMotors:Setup Driving||`` block and place it under the
``||basic:on start||`` loop. Set the ``||fwdMotors:left motor to servo1||``
 and ``||fwdMotors:right motor to servo2||``
Click on the ``||fwdMotors:+||`` symbol to set the bias to ``||fwdMotors: 0||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
0
)
```
## Step 3 
Click on the ``||logic:Logic||`` drawer and drag the ``||logic:if true then||`` block into the ``||basic:forever||`` loop.
Repeat this step 2 more times until there are 3 ``||logic:if true then||`` blocks in the ``||basic:forever||`` loop.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
0
)
basic.forever(function () {
    if (true) {
            }
    if (true) {
            }
    if (true) {
            }
})
```
## Step 4 
From ``||fwdSensors:Sensors||`` drawer, add ``||fwdSensors: line1 state is •||`` to the first ``||logic:if true||`` block.
Add ``||fwdSensors: line2 state is o||`` to the second ``||logic:if true||`` block.
For the last ``||logic:if true||`` condition add ``||fwdSensors: line3 state is •||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
0
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.lineSensorState.miss)) {
        }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        }
})
```
## Step 5 
For the ``||Electric Vehicle Prototype||`` to follow the line, its important
to make it turn either left or right to keep it on the path. Click on ``||fwdMotors: Motors||`` and
add the ``||fwdMotors: Turn 0 in place||`` block under the first ``||logic: if||`` 
``||fwdSensors:line1 state is •||`` ``||logic:then||`` and change the ``||fwdMotors:Turn 0||``
to ``||fwdMotors:5||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
0
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        fwdMotors.turn(5)
        }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.lineSensorState.miss)) {
            }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        })
```
## Step 6 
Click on ``||fwdMotors:Motors||`` to add ``||fwdMotors:Drive foward 50||`` block,
this is to drive the ``||Electric Vehicle Prototype||`` straight, and add it to the second
``||logic:if||`` ``||fwdSensors:line2 state is o||`` ``||logic:then||``.
Add the ``||fwdMotors: Turn 0 in place||`` block for the last ``||logic:if||``
``||fwdSensors:line3 state is •||`` ``||logic:then||``. Change the ``||fwdMotors:Turn 0||``
to ``||fwdMotors:-5||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
0
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        fwdMotors.turn(5)
            }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.lineSensorState.miss)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 20)
        }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        fwdMotors.turn(-5)
        }
})
```
## Step 7 
Click on the ``||basic:basic||`` drawer and add a ``||basic:pause 500 ms||`` block in 
each ``||logic:if then||`` condition. This allows for the ``||fwdSensors:Sensors||`` 
to detect if the ``||Electric Vehicle Prototype||`` is off track, and it instructs the ``||Robot||``
to turn towards the line.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
0
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        fwdMotors.turn(5)
        basic.pause(500)
    }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.lineSensorState.miss)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 20)
        basic.pause(500)
    }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        fwdMotors.turn(-5)
        basic.pause(500)
    }
})
```
## Step 8 
Download your code to test your Electric Vehicle Prototype.
Congratulations on completing your Electric Vehicle Prototype! - Go back to the lesson for more activities and extensions.
