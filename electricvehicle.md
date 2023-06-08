# Electric Vehicle Prototype
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
solar=github:climate-action-kits/pxt-fwd-edu
```
## Step 1 @showdialog
Plug your USB cable into the micro:bit and insert it into the 
Climate Action Kit board. 
![breakout board](https://raw.githubusercontent.com/mbakhtar/wind-turbine-lesson-tutorial/master/breakout-resized.png)

## Step 2 @showhint
Click on the button to the right of download and follow the steps to pair your micro:bit.
![pair gif](https://raw.githubusercontent.com/mbakhtar/iste-electric-vehicle-v1/master/pair%20microbit-280x203.gif)


## Step 3 
Click on the ``||fwdMotors:Motors||`` drawer, find and drag the
``||fwdMotors:Setup Driving||`` block to place it under the
``||basic:on start||`` loop.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo1,
)
```
## Step 4 
Change the ``||fwdMotors:right motor to servo2||``. 
Keep the ``||fwdMotors: left motor to servo1||``.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
```
## Step 5
Click on the ``||logic:Logic||`` drawer and find the ``||logic:if true then||`` block.
Drag and place it inside or under the ``||basic:forever||`` loop.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (true) {
            }
    })
```
## Step 6
Repeat the last step 2 more times to have 3 ``||logic:if true then||`` blocks 
in the ``||basic:forever||`` loop.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
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
## Step 7
From ``||fwdSensors:Sensors||`` drawer, add ``||fwdSensors: line1 state is •||`` 
to the first ``||logic:if true||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        }
    if (true) {
        }
    if (true) {
        }
})
```
## Step 8
Add ``||fwdSensors: line2 state is o||`` to the second ``||logic:if true||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.lineSensorState.miss)) {
        }
    if (true) {
        }
})
```
## Step 9
For the last ``||logic:if true||`` condition add ``||fwdSensors: line3 state is •||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
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
## Step 10
For the ``||Electric Vehicle Prototype||`` to follow the line, its important
to make it turn either left or right to keep it on the path. 
Click on ``||fwdMotors: Motors||`` and add the 
``||fwdMotors: Turn 0 in place||`` block under the first ``||logic: if||`` 
``||fwdSensors:line1 state is •||`` ``||logic:then||`` condition.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        fwdMotors.turn(0)
        }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.lineSensorState.miss)) {
            }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        })
```
## Step 11
Change the ``||fwdMotors:Turn 0||`` to ``||fwdMotors:5||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
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
## Step 12
Click on ``||fwdMotors:Motors||`` to add ``||fwdMotors:Drive forward 50||`` block,
this is to drive the ``||Electric Vehicle Prototype||`` straight, and add it to the second
``||logic:if||`` ``||fwdSensors:line2 state is o||`` ``||logic:then||``.
Change the ``||fwdMotors:Drive forward 50||`` to ``||fwdMotors:20||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        fwdMotors.turn(5)
            }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.lineSensorState.miss)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 20)
        }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        }
})
```
## Step 13
Add the ``||fwdMotors: Turn 0 in place||`` block for the last ``||logic:if||``
``||fwdSensors:line3 state is •||`` ``||logic:then||`` condition. 
Also change the ``||fwdMotors:Turn 0||`` to ``||fwdMotors:-5||``.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
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
## Step 14
Click on the ``||basic:Basic||`` drawer and find a ``||basic:pause 100 ms||``
block. Drag and drop it under or inside after the ``||fwdMotors:Turn 5 in place||`` block.
This allows for the ``||fwdSensors:Line Sensors||`` to detect if the 
``||Electric Vehicle Prototype||`` is off track, and it instructs the 
``||Robot||`` to turn towards the line/path.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        fwdMotors.turn(5)
        basic.pause(100)
    }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.lineSensorState.miss)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 20)
        }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        fwdMotors.turn(-5)
        }
})
```
## Step 15
Repeat the last step to add 2 more ``||basic:pause 100 ms||`` blocks.
Click on the ``||basic:basic||`` drawer and add a ``||basic:pause 100 ms||``
block inside and after ``||fwdMotors:Drive Forward at 50||`` block and
``||fwdMotors:Turn -5 in place||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        fwdMotors.turn(5)
        basic.pause(100)
    }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.lineSensorState.miss)) {
        fwdMotors.drive(fwdMotors.drivingDirection.forward, 20)
        basic.pause(100)
    }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.lineSensorState.hit)) {
        fwdMotors.turn(-5)
        basic.pause(100)
    }
})
```
## Step 16
Click on the ``||fwdMotors:+||`` symbol of the ``||fwdMotors:Setup Driving||``
block nested in the ``||basic:on start||`` block
to set the bias to ``||fwdMotors: 0||``.
Also change ``||basic:pause 100 ms||`` to ``||basic:500 ms||``of all the 
``||basic:pause||`` blocks. This step finalises your code.
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
## Step 17
``|Download|`` and test your code. 
Congratulations on completing your Electric Vehicle Prototype! - Go back to the lesson for more activities and extensions.
