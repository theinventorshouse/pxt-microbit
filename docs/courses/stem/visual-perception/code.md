# Code

Have you ever tried to checking your vision lately? Let's try creating code dynamic to identify when the line changes from blinking LEDs to the perception of being a solid LED diagonal line!

Welcome! This activity will use the X and Y coordinates to slowly join two opposite corners of a the LEDs square display. Create an  `on start` that will set the initial pause.  

```blocks
let pause = 0
pause = 50

```

We want to create a `forever` loop that will continously display the LEDs.


```blocks
basic.forever(() => {
	
})


```

The micro:bit will create a LED with plot x and y. We want to create a for loop and set to index. The index will be set from 0 to 4.  

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
basic.forever(() => {    acceleration = input.acceleration(Dimension.Z)    
acceleration = Math.abs(input.acceleration(Dimension.Z))   
acceleration = input.acceleration(Dimension.Z) / 4}) 

```

Now let's use acceleration value to set the brightness of the BBC micro:bi using `plot bar graph`.


```blocks
let acceleration = 0
basic.forever(() => {
    acceleration = input.acceleration(Dimension.Z)
    acceleration = Math.abs(input.acceleration(Dimension.Z))
    acceleration = input.acceleration(Dimension.Z) / 4
    led.plotBarGraph(
    acceleration,
    0
    )
})



```

### Challenge 1


![](\static\mb\courses\stem\acc\acc_challenge1.jpg)

Spin BBC micro:bit in a dark room. Move the BBC micro:bit like a fidget spinner and produce a slow image that captures the pattern of the BBC micro:bit LEDs.

### Challenge 2

Replace "z" in `acceleration(z)` with "x" or "y". Changing the axis will cause the BBC micro:bit to measure the force in a different direction. What differences in the resulting pattern does this replacement make`

* click *Download* to see if the code works as expected.
