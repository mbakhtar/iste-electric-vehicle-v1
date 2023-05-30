# Electric Vehicle
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
solar=github:climate-action-kits/pxt-fwd-edu
```
## Step 1 
Plug your USB cable into the micro:bit and insert it into the 
Climate Action Kit board. Click on the button to the right of 
download and follow the steps to pair your micro:bit.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo2,
0
)
basic.showLeds(`
    . . . . .
    # . . # .
    # # # # #
    # . . # .
    . . . . .
    `)
basic.showLeds(`
    . . . . .
    . # . . #
    . # # # #
    . # . . #
    . . . . .
    `)
basic.showLeds(`
    . . . . .
    . . # . .
    . . # # #
    . . # . .
    . . . . .
    `)
basic.showLeds(`
    . . . . .
    . . . # .
    . . . # #
    . . . # .
    . . . . .
    `)
basic.showLeds(`
    . . . . .
    . . . . #
    . . . . #
    . . . . #
    . . . . .
    `)
basic.showLeds(`
    . . . . .
    . . . . .
    . . . . .
    . . . . .
    . . . . .
    `)
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

## Step 2 
Create a ``||Variables:Variable position||`` 
and nest ``||Variables:set position to -90||`` 
under ``||basic:on start||`` block
Now nest an ``||logic:If true then else||`` 
block under the ``||basic:forever||`` loop
```blocks
let position = -90
basic.forever(function(){
    if(true){
    }
    else{
    }
})
```
## Step 3 
Add a ``||logic:comparison block||`` from the 
``||logic:Logic drawer||`` place it in the true
condition of the ``||logic: if then else||`` loop
Insert the block ``||fwdSensors:solar1 light level %||`` on the left side
and insert ``||75||`` on the right side of the ``||logic:comparison block||``
```blocks
let position = -90
basic.forever(function(){
    if(fwdSensors.solar1.fwdLightLevel() > 75){
    }
    else{
    }
})
```
## Step 4 
If the condition is true add ``||basic:show icon||`` block and 
select ``||basic:target icon||``. 
To stop the ``||Solar Array||`` from scanning 
for the sunlight, go to ``||fwdMotors:set servo1 off||``. 
This indicates the ``||Solar Array||`` 
is facing the sun and receiving maximum light
```blocks
let position = -90
basic.forever(function () {
    if (fwdSensors.solar1.fwdLightLevel() > 75) {
    basic.showIcon(IconNames.Target)
    fwdMotors.servo1.fwdSetEnabled(false)
    } 
    else {}
})
```
## Step 5 
If the condition is false add ``||basic:show icon||`` block under the 
``||logic:else||`` and select ``||basic: small diamond icon||``.
Now add ``||Variables:change position by 10||`` block under 
the ``||basic:small diamond icon||``
Add ``||logic:if true then||`` block under the 
``||logic:else||`` condition below the 
``||Variables:change position by 10||``
```blocks
let position = -90
basic.forever(function () {
    if (fwdSensors.solar1.fwdLightLevel() > 75) {
        basic.showIcon(IconNames.Target)
        fwdMotors.servo1.fwdSetEnabled(false)
    } else {
        basic.showIcon(IconNames.SmallDiamond)
        position += 10
        if () {
            }
        }
})
```
## Step 6 
For the true condition replace it by a ``||logic:comparison||`` block
For the comparison add ``||Variables:position||`` on the left side and 
compare with ``||90||``
For the true condition add ``||Variables:set position to -90||`` 
nested under the ``||logic:if position>90 then||``
```blocks
let position = -90
basic.forever(function () {
    if (fwdSensors.solar1.fwdLightLevel() > 75) {
        basic.showIcon(IconNames.Target)
        fwdMotors.servo1.fwdSetEnabled(false)
    } else {
        basic.showIcon(IconNames.SmallDiamond)
        position += 10
        if (position > 90) {
            position = -90
        }
        
    }
})
```

## Step 7 
Add ``||fwdMotors: set servo1 angle to||`` block and insert 
``||Variables:position||`` block in it. This is placed
after the ``||logic:if then||`` block 
Also add a ``||basic:pause||`` block and set it to ``||basic:20ms||``
```blocks
let position = -90
basic.forever(function () {
    if (fwdSensors.solar1.fwdLightLevel() > 75) {
        basic.showIcon(IconNames.Target)
        fwdMotors.servo1.fwdSetEnabled(false)
    } else {
        basic.showIcon(IconNames.SmallDiamond)
        position += 10
        if (position > 90) {
            position = -90
        }
        fwdMotors.servo1.fwdSetAngle(position)
        basic.pause(20)
    }
})
```
## Step 8 
This is the final code
```blocks
let position = -90
fwdMotors.servo1.fwdSetEnabled(false)
basic.forever(function () {
    if (fwdSensors.solar1.fwdLightLevel() > 75) {
        basic.showIcon(IconNames.Target)
        fwdMotors.servo1.fwdSetEnabled(false)
    } else {
        basic.showIcon(IconNames.SmallDiamond)
        position += 10
        if (position > 90) {
            position = -90
        }
        fwdMotors.servo1.fwdSetAngle(position)
        basic.pause(20)
    }
})
```
Congratulations, you did it!