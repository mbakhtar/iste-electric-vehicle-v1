# Electric Vehicle
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
solar=github:climate-action-kits/pxt-fwd-edu
```
## Step 1 
Plug your USB cable into the micro:bit and insert it into the 
Climate Action Kit board. Click on the button to the right of 
download and follow the steps to pair your micro:bit.

## Step 2 
Click on the ``||fwdMotors:Motors||`` drawer and drag
``||fwdMotors:Setup Driving||`` block and place it under
``||basic:on start||`` loop. Set ``||fwdMotors:left motor to servo1||``
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
Click on the ``||logic:Logic||`` drawer and drag ``||logic:if true then||`` block.
Place three ``||logic:if true then||`` block inside the ``||basic:forever||`` loop.
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
Add ``||fwdSensors: line1 state is •||`` to the first ``||logic:if true||`` block.
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
For the ``||Line Follower Robot||`` to follow the line, its important
to make it turn either left or right to keep it on the path. Click on ``||fwdMotors: Motors||``
add ``||fwdMotors: Turn 0 in place||`` block under the first ``||logic: if||`` 
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
this is to drive the ``||Line Follower Robot||`` straight, in the middle or the second
``||logic:if||`` ``||fwdSensors:line2 state is o||`` ``||logic:then||``.
Add ``||fwdMotors: Turn 0 in place||`` block for the last ``||logic:if||``
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
Click on ``||basic:basic||`` drawer and add ``||basic:pause 500 ms||`` block in 
each ``||logic:if then||`` condition. This allows for the ``||fwdSensors:Sensors||`` 
to detect the ``||Line Follower Robot||`` is off track/path and instruct the ``||Robot||``
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
Download your code to test your Line Follower Robot.
Congratulations on completing your Automatic Irrigation System!
Everyone can use tech to make the world a better place! Go back to the Forward Edu lesson for more activities and extensions.
