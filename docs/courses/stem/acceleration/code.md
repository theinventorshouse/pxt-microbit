# Code

Have you ever tried to making your fidget spinner? Let's try creating code dynamic fidget spinner!

Welcome! This activity will create a pendulum that glows using acceleration. Create a `forever` loop that will constantly display the appropriate brightness on the LED display.  

```blocks
basic.forever(() => {
	
})

```

We want to measure the acceleration on the y axis and store the value in a variable. The `acceleration (z)` fucntion will provide the value.


```blocks
let acceleration = 0
basic.forever(() => {
    acceleration = input.acceleration(Dimension.Z)
})


```

Since the micro:bit will be swinging in a clockwise or counterclockwise path, the acceleration will only be positive half of the time. Thus, to always get a positive value, we want to take the `absolute` value of the acceleration. 

```blocks
let acceleration = 0
basic.forever(() => {
    acceleration = input.acceleration(Dimension.Z)
    acceleration = Math.abs(input.acceleration(Dimension.Z))
})

```

The function `accelration(z)` returns a number between 0 and 1024. We want to use this value for the brightness of the BBC micro:bit, but the `set brightness()` only accepts a value beetween 0 and 256. Thus, we need to divide the acceleration by 4 to ensure we will be in the appropriate range. 

```blocks
let acceleration = 0
basic.forever(() => {    acceleration = input.acceleration(Dimension.Z)    acceleration = Math.abs(input.acceleration(Dimension.Z))    acceleration = input.acceleration(Dimension.Z) / 4}) 

```
let acceleration = 0
basic.forever(() => {
    acceleration = input.acceleration(Dimension.Z)
    acceleration = Math.abs(input.acceleration(Dimension.Z))
    acceleration = input.acceleration(Dimension.Z) / 4
})

```
  

We want to code the notes that will be played `on pin pressed`. We click on the Input drawer then insert a `for loop` that will increment by *i*. Click on the Variables drawer. Add `set item` block. Rename the variable block to "sound." Then add a Maths block to increase the variable sound from the note frequency of block `A` to `A` plus 25.Modify your code so that your code looks like this

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
let sound = music.noteFrequency(Note.A);

input.onPinPressed(TouchPin.P1, () => {
    for (let i = 0; i < 4; i++) {
        sound = sound + 25
    }
})

input.onPinPressed(TouchPin.P2, () => {
    for (let i = 0; i < 4; i++) {
        sound = sound - 25
    }
})
```

The code for the radio dashboard activity is available here

Go to https://makecode.microbit.org/examples/radio-dashboard.

* click *Download* to see if the code works as expected.
