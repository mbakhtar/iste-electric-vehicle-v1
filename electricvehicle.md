# Electric Vehicle Prototype
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
solar=github:climate-action-kits/pxt-fwd-edu
```
## @showdialog
Welcome to Electric Vehicle Coding Tutorial
![built project](https://raw.githubusercontent.com/mbakhtar/iste-electric-vehicle-v1/master/project%20-%20electric%20car.png)

## Step 1 @showdialog
Plug your USB cable into the micro:bit and insert it into the 
Climate Action Kit board. 
![breakout board](https://raw.githubusercontent.com/mbakhtar/wind-turbine-lesson-tutorial/master/breakout-resized.png)

## Step 2 @showhint
Click three dots besides ``|Download|`` button and follow the steps to pair your micro:bit.
![pair gif](https://raw.githubusercontent.com/mbakhtar/iste-electric-vehicle-v1/master/pair%20microbit-280x203.gif)

## Step 3 
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors:Setup Driving||`` block inside ``||basic:on start||`` loop.
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
Click ``||logic:Logic||`` drag and drop ``||logic:if true then||`` block inside ``||basic:forever||`` loop.
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
Click ``||logic:Logic||`` drag and drop ``||logic:if true then||`` block under the 1st ``||logic:if true then||`` block
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
})
```
## Step 7
Click ``||logic:Logic||`` drag and drop ``||logic:if true then||`` block under the 2nd ``||logic:if true then||`` block
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
Click ``||fwdSensors:Sensors||`` drag and drop ``||fwdSensors: line1 state is •||`` to replace ``||logic:true||`` condition of 1st ``||logic:if true then||`` block.
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
Click ``||fwdSensors:Sensors||`` drag and drop ``||fwdSensors: line2 state is o||`` to replace ``||logic:true||`` condition of 2nd ``||logic:if true then||`` block.
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
Click ``||fwdSensors:Sensors||`` drag and drop ``||fwdSensors: line3 state is •||`` to replace ``||logic:true||`` condition of 3rd ``||logic:if true then||`` block.
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
Click ``||fwdMotors: Motors||`` drag and drop ``||fwdMotors: Turn 0 in place||`` block inside 1st ``||logic: if||`` 
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
Change ``||fwdMotors:Turn 0||`` to ``||fwdMotors:5||``
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
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors:Drive forward 50||`` block inside 2nd
``||logic:if||`` ``||fwdSensors:line2 state is o||`` ``||logic:then||`` condition.
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
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors: Turn 0 in place||`` block inside 3rd ``||logic:if||``
``||fwdSensors:line3 state is •||`` ``||logic:then||`` condition. 
Change the ``||fwdMotors:Turn 0||`` to ``||fwdMotors:-5||``.
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
Click ``||basic:Basic||`` drag and drop ``||basic:pause (ms) 100||`` block under ``||fwdMotors:Turn 5 in place||`` block.
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
Click ``||basic:basic||`` drag and drop ``||basic:pause (ms) 100||``
block under ``||fwdMotors:Drive Forward at 50||`` block.
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
    }
})
```
## Step 16
Click ``||basic:basic||`` drag and drop ``||basic:pause (ms) 100||``
block under ``||fwdMotors:Turn -5 in place||`` block.
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
## Step 17
Click ``||fwdMotors:+||`` on ``||fwdMotors:Setup Driving||``
block inside ``||basic:on start||`` block. Set bias to ``||fwdMotors: 0||``.
Change ``||basic:pause (ms) 100||`` to ``||basic:500||`` for all 
``||basic:pause||`` blocks.
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
## Step 18
``|Download|`` and test your code. 
Congratulations on completing your Electric Vehicle Prototype! - Go back to the lesson for more activities and extensions.
