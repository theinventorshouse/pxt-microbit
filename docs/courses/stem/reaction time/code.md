# Code

Have you ever tried to making your plant to be interacative? Let's try making a soil moisture sensor!

Soil moisture sensors work by measuring the level of current flowing between two electrodes immersed in soil. Students can investigate and develop their own
moisture sensor using common materials such as aluminium foil, metal roads, insulating tape, foam blocks, insulated wire etc. They can be tested before use by
attaching a bulb and cell, checking that the bulb lights up when the electrodes are inserted into damp soil.

The moisture sensor is then attached
to the micro:bit edge connector with
crocodile clips. 


```blocks
let sound = music.noteFrequency(Note.A);
```

We want to play music on pin pressed in order to register an event handler that will execute whenever when you run a script and click pin 1 on the simulator. We must start by opening the Input drawer and adding `on pin pressed` P1. Modify your code so that your code looks like this.

```blocks
let sound = music.noteFrequency(Note.A);
input.onPinPressed(TouchPin.P1, () => {

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
