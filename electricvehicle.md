# Electric Vehicle Prototype
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
solar=github:climate-action-kits/pxt-fwd-edu
```
## Step 1 @showdialog
Welcome to Electric Vehicle Coding Tutorial
![built project](https://raw.githubusercontent.com/mbakhtar/iste-electric-vehicle-v1/master/project%20-%20electric%20car-400.png)

## Step 2 @showdialog
Plug your USB cable into the micro:bit. 
![breakout board](https://raw.githubusercontent.com/mbakhtar/tree-seeder-v1/master/connect-microbit.gif)

## Step 3 @showdialog
Insert it into the Climate Action Kit board. 
![breakout board](https://raw.githubusercontent.com/mbakhtar/wind-turbine-lesson-tutorial/master/breakout-resized.png)

## Step 4 @showhint
Click three dots besides ``|Download|`` button and follow the steps to pair your micro:bit.
![pair gif](https://raw.githubusercontent.com/mbakhtar/iste-electric-vehicle-v1/master/pair%20microbit-280x203.gif)

## Step 5
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors:Setup Driving||`` block inside ``||basic:on start||`` loop.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo1,
)
```
## Step 6
Change the ``||fwdMotors:right motor to servo2||``. 
Keep the ``||fwdMotors: left motor to servo1||``.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
```
## Step 7
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
## Step 8
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
## Step 9
Click ``||logic:Logic||`` drag and drop ``||logic:if true then||`` block under the 2nd ``||logic:if true then||`` block. _Note: Three ``||logic:if true then||`` blocks are used._
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
## Step 10
Click ``||fwdSensors:Sensors||`` drag and drop ``||fwdSensors: line1 state is •||`` to replace ``||logic:true||`` condition of 1st ``||logic:if true then||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        }
    if (true) {
        }
    if (true) {
        }
})
```
## Step 11
Click ``||fwdSensors:Sensors||`` drag and drop ``||fwdSensors: line2 state is o||`` to replace ``||logic:true||`` condition of 2nd ``||logic:if true then||`` block. _Note: Use drop down menu to change line number._
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.LineSensorState.Miss)) {
        }
    if (true) {
        }
})
```
## Step 12
Click ``||fwdSensors:Sensors||`` drag and drop ``||fwdSensors: line3 state is •||`` to replace ``||logic:true||`` condition of 3rd ``||logic:if true then||`` block.  _Note: Use drop down menu to change line number._
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.LineSensorState.Miss)) {
        }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        }
})
```
## Step 13
Click ``||fwdMotors: Motors||`` drag and drop ``||fwdMotors: Turn 0 in place||`` block inside 1st ``||logic: if||`` 
``||fwdSensors:line1 state is •||`` ``||logic:then||`` condition.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(0)
        }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.LineSensorState.Miss)) {
            }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        })
```
## Step 14
Change ``||fwdMotors:Turn 0||`` to ``||fwdMotors:5||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(5)
        }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.LineSensorState.Miss)) {
            }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        })
```
## Step 15
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors:Drive forward 50||`` block inside 2nd
``||logic:if||`` ``||fwdSensors:line2 state is o||`` ``||logic:then||`` condition.
Change the ``||fwdMotors:Drive forward 50||`` to ``||fwdMotors:20||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(5)
            }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.LineSensorState.Miss)) {
        fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 20)
        }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        }
})
```
## Step 16
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors: Turn 0 in place||`` block inside 3rd ``||logic:if||``
``||fwdSensors:line3 state is •||`` ``||logic:then||`` condition. 
Change the ``||fwdMotors:Turn 0||`` to ``||fwdMotors:-5||``.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(5)
            }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.LineSensorState.Miss)) {
        fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 20)
        }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(-5)
        }
})
```
## Step 17
Click ``||basic:Basic||`` drag and drop ``||basic:pause (ms) 100||`` block under ``||fwdMotors:Turn 5 in place||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(5)
        basic.pause(100)
    }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.LineSensorState.Miss)) {
        fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 20)
        }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(-5)
        }
})
```
## Step 18
Click ``||basic:basic||`` drag and drop ``||basic:pause (ms) 100||``
block under ``||fwdMotors:Drive Forward at 20||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(5)
        basic.pause(100)
    }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.LineSensorState.Miss)) {
        fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 20)
        basic.pause(100)
    }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(-5)
    }
})
```
## Step 19
Click ``||basic:basic||`` drag and drop ``||basic:pause (ms) 100||``
block under ``||fwdMotors:Turn -5 in place||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
)
basic.forever(function () {
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(5)
        basic.pause(100)
    }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.LineSensorState.Miss)) {
        fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 20)
        basic.pause(100)
    }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(-5)
        basic.pause(100)
    }
})
```
## Step 20
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
    if (fwdSensors.line1.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(5)
        basic.pause(500)
    }
    if (fwdSensors.line2.fwdIsLineSensorState(fwdSensors.LineSensorState.Miss)) {
        fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 20)
        basic.pause(500)
    }
    if (fwdSensors.line3.fwdIsLineSensorState(fwdSensors.LineSensorState.Hit)) {
        fwdMotors.turn(-5)
        basic.pause(500)
    }
})
```
## Step 21
``|Download|`` and test your code. 
Congratulations on completing your Electric Vehicle Prototype! - Go back to the lesson for more activities and extensions.
Want to check your code click [here](https://makecode.microbit.org/S00697-39074-44503-13255).
