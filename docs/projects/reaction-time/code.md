# Code
### @description code to make the Reaction Time interactive

### ~avatar avatar

Add code to make the Reaction Time interactive.

### ~

## Duration: ~30 minutes

## Step 1: build reaction time game


In order for the Reaction Game to follow the rules for determining the player's reaction speed, we need to set variables to store data. Then we will rename the variables to be “start”, “end”, “false_start”, and “running”. Then set the value of the variable “start” and “end” to 0. Then set the value of the variable “false_start” and “running” to false. Modify your code so that your code looks like this.

. In the code below:
- the user pressed button ``A`` to switch the servo to 180 degrees (to close the mouth of Milky Monster). 
- the user pressed button ``B`` to switch the servo to 0 degrees (to open the mouth of Milky Monster). 

Have you ever tried to build the boardgame Operation? Let's try making a game where you control atmospheric temperature!

Experiment 1:

We will register an event handler on the aluminum foil that will execute when two things occur: first, the alligator clip will attach to aluminum foil and GND while the other side of the alligator clip is attached to the aluminum.



```blocks
let start = 0

let end = 0

let false_start = false

let running = false

running = false

false_start = false

end = 0

start = 0


```

We want to display a countdown timer on pin pressed in order to register an event handler that will execute whenever when you run a script and click pin 0 on the simulator. We must start by opening the Input drawer and adding on pin pressed P0. Modify your code so that your code looks like this.

```blocks
let start = 0

let end = 0

let false_start = false

let running = false

running = false

false_start = false

end = 0

start = 0


input.onPinPressed(TouchPin.P0, () => {
    
    }
})
```

We want to code the countdown timer that will be played on pin pressed. We click on the Basics drawer then insert three show number blocks to visually display the countdown: 3 2 1. Then we want to add a Basic block clear screen, which is found under Basic ... (more Basic blocks). Modify your code so that your code looks like this:

```blocks
let start = 0

let end = 0

let false_start = false

let running = false

input.onPinPressed(TouchPin.P0, () => {
    
	basic.showNumber(3)
    
	basic.showNumber(2)
    
	basic.showNumber(1)
    
	basic.clearScreen()
    
    }
})
```

* click Download to see if the code works as expected.

We want to set running to false and set false start to false. This occurs on pin pressed. Modify your code so that your code looks like this:

```blocks
let end = 0

let start = 0

let false_start = false

let running = false

input.onPinPressed(TouchPin.P0, () => {
    
basic.showNumber(3)
    
basic.showNumber(2)
    
basic.showNumber(1)
    
basic.clearScreen()
    
running = false
    
false_start = false
})
```

We want to set a random pause before the random LED is being displayed. Modify your code so that your code looks like this:

```blocks
let end = 0

let false_start = false

let running = false

let start = 0

input.onPinPressed(TouchPin.P0, () => {
    
basic.showNumber(3)
    
basic.showNumber(2)
    
basic.showNumber(1)
   
basic.clearScreen()
    
running = false
    
false_start = false
    
basic.pause(1000 + Math.random(2000))

})
```

We want to introduce the game on pin pressed 0 that displays a randomly placed LED on the x and y coordinates. The randomly generated LED will be displayed only  when there has not been a false start by the player. Modify your code so that your code looks like this:

```blocks
let start = 0

let end = 0

let false_start = false

let running = false

input.onPinPressed(TouchPin.P0, () => {
    
basic.showNumber(3)
    
basic.showNumber(2)
    
basic.showNumber(1)
    
basic.clearScreen()
    
running = false
    
false_start = false
    
basic.pause(1000 + Math.random(2000))
    
if (!(false_start)) {
        
start = input.runningTime()
        
running = true
        
led.stopAnimation()
        
basic.clearScreen()
        
led.plot(Math.random(5), Math.random(5))
    }
})
```

We want to display one of two images on pin pressed 1. The first image will display only if the player correctly completes the circuit between GND and P1 after the randomly generated LED appears. The seconde image will display only if the player completes a circuit between GND and P1 on a false start. Modify your code so that your code looks like this:  


```blocks
let start = 0
let end = 0
let false_start = false
let running = false
input.onPinPressed(TouchPin.P0, () => {
    basic.showNumber(3)
    basic.showNumber(2)
    basic.showNumber(1)
    basic.clearScreen()
    running = false
    false_start = false
    basic.pause(1000 + Math.random(2000))
    if (!(false_start)) {
        start = input.runningTime()
        running = true
        led.stopAnimation()
        basic.clearScreen()
        led.plot(Math.random(5), Math.random(5))
    }
})
input.onPinPressed(TouchPin.P1, () => {
    if (running) {
        running = false
        end = input.runningTime()
        basic.showLeds(`
            # # . . .
            # # . . .
            # # . . .
            # # . . .
            # # . . .
            `)
        basic.pause(1000)
        basic.showNumber(end - start)
    } else {
        false_start = true
        basic.showLeds(`
            . . . . .
            # . # . .
            . # . . .
            # . # . .
            . . . . .
            `)
    }
})
```

Experiment 2: Play the game with a peer. Both players share the GND and each player has their own Pin to press. The second Player is represented with P2. You can find the code for this below:


```blocks
let start = 0
let end = 0
let false_start = false
let running = false
input.onPinPressed(TouchPin.P0, () => {
    basic.showNumber(3)
    basic.showNumber(2)
    basic.showNumber(1)
    basic.clearScreen()
    running = false
    false_start = false
    basic.pause(1000 + Math.random(2000))
    if (!(false_start)) {
        start = input.runningTime()
        running = true
        led.stopAnimation()
        basic.clearScreen()
        led.plot(Math.random(5), Math.random(5))
    }
})
input.onPinPressed(TouchPin.P1, () => {
    if (running) {
        running = false
        end = input.runningTime()
        basic.showLeds(`
            # # . . .
            # # . . .
            # # . . .
            # # . . .
            # # . . .
            `)
        basic.pause(1000)
        basic.showNumber(end - start)
    } else {
        false_start = true
        basic.showLeds(`
            . . . . .
            # . # . .
            . # . . .
            # . # . .
            . . . . .
            `)
    }
})
input.onPinPressed(TouchPin.P2, () => {
    if (running) {
        running = false
        end = input.runningTime()
        basic.showLeds(`
            . . . # #
            . . . # #
            . . . # #
            . . . # #
            . . . # #
            `)
        basic.pause(1000)
        basic.showNumber(end - start)
    } else {
        false_start = true
        basic.showLeds(`
            . . . . .
            . . # . #
            . . . # .
            . . # . #
            . . . . .
            `)
    }
})

```

* click *Download* to see if the code works as expected.
