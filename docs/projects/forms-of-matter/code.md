# Code  

Have you ever tried to build the boardgame "Operation"? Let's try making a game where you control atmospheric temperature!

Experiment 1:

Let’s start by adding variables where you can store data. Then rename the variables to be “temperature” and “atmospheric_temperature”. Then set the value of the variable “temperature” and “atmospheric_temperature” to 0.

```blocks
let temperature = 0
let ambient_temperature = 0

```

We will register an event handler on the aluminum foil that will execute when two things occur: first, the alligator clip will attach to aluminum foil doppler that connects to another pin.

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
let temperature = 0

let ambient_temperature = 0

input.onGesture(Gesture.Shake, () => {
    
temperature += 50
    
basic.showIcon(IconNames.Triangle)
})

basic.forever(() => {
    
if (temperature < ambient_temperature) {
        
temperature += 20
    } 
else {
        
temperature += -20
    
}
    
if (temperature < 32) {
        
basic.showIcon(IconNames.Square)
    } 
else if (temperature < 212) {
        
basic.showIcon(IconNames.Umbrella)
    } 
else {
        
basic.showIcon(IconNames.Chessboard)
    }
   
basic.clearScreen()
    
basic.pause(100)
})

input.onPinPressed(TouchPin.P2, () => {
    
ambient_temperature = 0
    
basic.showString("SOLID")
})

input.onPinPressed(TouchPin.P1, () => {
    
ambient_temperature = 80
    
basic.showString("LIQUID")
})

input.onPinPressed(TouchPin.P0, () => {
    
ambient_temperature = 250
    
basic.showString("GAS")
})

ambient_temperature = 100

temperature = 100

```

* click *Download* to see if the code works as expected.
