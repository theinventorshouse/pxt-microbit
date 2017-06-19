# Code

Have you ever tried to test your ability to focus by making your own reaction time game? Let's try making a reaction time!


Experiment 1:

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

We want to play the reaction game when connecting a circuit between GND and P1.

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

Experiment 2:

```blocks
let sound = music.noteFrequency(Note.A);
input.onPinPressed(TouchPin.P1, () => {
    for (let i = 0; i < 4; i++) {
        sound = sound + 25
    }
})
```


* click *Download* to see if the code works as expected.



Let's include a second sound `on pin pressed` *P2*. To do this, you need to add the same blocks as the banana keyboard activity. However, you must change alter `on pin pressed` from P1 to P2. Additionally, you must *decrease* the frequency of the variable "sound" by 25. Modify your code so that your code looks like this. You will need to include a second banana to a alligator (spring) clip in the same procedure as the first activity. 

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
