# Code

Have you ever tried to detect acceleration? Let's try creating code for an acceleration experiment!

Welcome! This activity will create an experiment using acceleration. Create a `forever` loop that will constantly display the appropriate brightness on the LED display.  

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
basic.forever(() => {    acceleration = input.acceleration(Dimension.Y)    
acceleration = Math.abs(input.acceleration(Dimension.Z))   
acceleration = input.acceleration(Dimension.Y) / 4}) 

```

Now let's use acceleration value to set the brightness of the BBC micro:bi using `plot bar graph`.


```blocks
let acceleration = 0
basic.forever(() => {
    acceleration = input.acceleration(Dimension.Z)
    acceleration = Math.abs(input.acceleration(Dimension.Y))
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
