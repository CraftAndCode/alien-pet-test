# Alien Pet

```package
core
radio
microphone
proportionalFont=github:lwchkg/pxt-proportional-font
```
```template

let cleans = 0
let plays = 0
let jumps = 0
soundExpression.hello.play()
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # # # # #
    . . . . .
    `)
basic.pause(2000)
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # . . . #
    . # # # .
    `)
while (!(input.buttonIsPressed(Button.A) || input.buttonIsPressed(Button.B))) {
    basic.pause(1)
}
soundExpression.giggle.play()
let petmood = randint(1, 4)
basic.forever(function () {
    while (petmood == 5) {
        basic.showLeds(`
            . . # . .
            . # . # .
            . . . # .
            . . # . .
            . . # . .
            `)
        soundExpression.soaring.playUntilDone()
        basic.pause(2000)
        petmood = randint(1, 4)
    }
})

basic.forever(function () {
    while (petmood != 5) {
        if (petmood == 1) {
            basic.clearScreen()
            proportionalFont.showString("Jump!  ", 150)
            basic.clearScreen()
            jumps = randint(4, 8)
            for (let index = 0; index <= jumps; index++) {
                basic.showNumber(jumps - index + 1)
                while (!(input.isGesture(Gesture.FreeFall))) {
                    basic.pause(1)
                }
                soundExpression.slide.playUntilDone()
            }
        } else if (petmood == 2) {
            basic.clearScreen()
            proportionalFont.showString("Play!  ", 150)
            basic.clearScreen()
            plays = randint(0, 9)
            for (let index2 = 0; index2 <= plays; index2++) {
                if (Math.randomBoolean()) {
                    basic.showArrow(ArrowNames.West)
                    while (!(input.buttonIsPressed(Button.A))) {
                        basic.pause(1)
                    }
                    music.playTone(262, music.beat(BeatFraction.Quarter))
                } else {
                    basic.showArrow(ArrowNames.East)
                    while (!(input.buttonIsPressed(Button.B))) {
                        basic.pause(1)
                    }
                    music.playTone(392, music.beat(BeatFraction.Quarter))
                }
                basic.clearScreen()
                basic.pause(100)
            }
        } else if (petmood == 3) {
            basic.clearScreen()
            proportionalFont.showString("Light!  ", 150)
            basic.clearScreen()
            while (!(input.lightLevel() >= 150)) {
                basic.pause(1)
            }
        } else if (petmood == 4) {
            basic.clearScreen()
            proportionalFont.showString("Clean!  ", 150)
            basic.clearScreen()
            cleans = randint(63, 511)
            for (let index3 = 0; index3 <= cleans; index3++) {
                led.plotBarGraph(
                index3,
                cleans
                )
                while (!(input.logoIsPressed())) {
                    music.stopAllSounds()
                    basic.showArrow(ArrowNames.North)
                    basic.clearScreen()
                    basic.pause(100)
                    index3 = 0
                }
                music.ringTone(131 + index3)
                basic.pause(10)
            }
            music.stopAllSounds()
        }
        soundExpression.happy.play()
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            # . . . #
            . # # # .
            `)
        basic.pause(2000)
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            # # # # #
            . . . . .
            `)
        basic.pause(2000)
        soundExpression.sad.play()
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            . # # # .
            # . . . #
            `)
        basic.pause(2000)
        petmood = randint(1, 5)
    }
})

```

```blocks
let cleans = 0
let plays = 0
let jumps = 0
soundExpression.hello.play()
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # # # # #
    . . . . .
    `)
basic.pause(2000)
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # . . . #
    . # # # .
    `)
while (!(input.buttonIsPressed(Button.A) || input.buttonIsPressed(Button.B))) {
    basic.pause(1)
}
soundExpression.giggle.play()
let petmood = randint(1, 4)
basic.forever(function () {
    while (petmood == 5) {
        basic.showLeds(`
            . . # . .
            . # . # .
            . . . # .
            . . # . .
            . . # . .
            `)
        soundExpression.soaring.playUntilDone()
        basic.pause(2000)
        petmood = randint(1, 4)
    }
})
basic.forever(function () {
    while (petmood != 5) {
        if (petmood == 1) {
            basic.clearScreen()
            proportionalFont.showString("Jump!  ", 150)
            basic.clearScreen()
            jumps = randint(4, 8)
            for (let index = 0; index <= jumps; index++) {
                basic.showNumber(jumps - index + 1)
                while (!(input.isGesture(Gesture.FreeFall))) {
                    basic.pause(1)
                }
                soundExpression.slide.playUntilDone()
            }
        } else if (petmood == 2) {
            basic.clearScreen()
            proportionalFont.showString("Play!  ", 150)
            basic.clearScreen()
            plays = randint(0, 9)
            for (let index2 = 0; index2 <= plays; index2++) {
                if (Math.randomBoolean()) {
                    basic.showArrow(ArrowNames.West)
                    while (!(input.buttonIsPressed(Button.A))) {
                        basic.pause(1)
                    }
                    music.playTone(262, music.beat(BeatFraction.Quarter))
                } else {
                    basic.showArrow(ArrowNames.East)
                    while (!(input.buttonIsPressed(Button.B))) {
                        basic.pause(1)
                    }
                    music.playTone(392, music.beat(BeatFraction.Quarter))
                }
                basic.clearScreen()
                basic.pause(100)
            }
        } else if (petmood == 3) {
            basic.clearScreen()
            proportionalFont.showString("Light!  ", 150)
            basic.clearScreen()
            while (!(input.lightLevel() >= 150)) {
                basic.pause(1)
            }
        } else if (petmood == 4) {
            basic.clearScreen()
            proportionalFont.showString("Clean!  ", 150)
            basic.clearScreen()
            cleans = randint(63, 511)
            for (let index3 = 0; index3 <= cleans; index3++) {
                led.plotBarGraph(
                index3,
                cleans
                )
                while (!(input.logoIsPressed())) {
                    music.stopAllSounds()
                    basic.showArrow(ArrowNames.North)
                    basic.clearScreen()
                    basic.pause(100)
                    index3 = 0
                }
                music.ringTone(131 + index3)
                basic.pause(10)
            }
            music.stopAllSounds()
        }
        soundExpression.happy.play()
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            # . . . #
            . # # # .
            `)
        basic.pause(2000)
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            # # # # #
            . . . . .
            `)
        basic.pause(2000)
        soundExpression.sad.play()
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            . # # # .
            # . . . #
            `)
        basic.pause(2000)
        petmood = randint(1, 5)
    }
})
```


## Step 0 @showDialog

Hello! This is a program for your Alien Pet. Let's modify it!

## Step 1 @showHint
### Changing Pet's expressions
You can control pet's facial expressions. First, find this place in the code:
```blocks
soundExpression.hello.play()
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # # # # #
    . . . . .
    `)
basic.pause(2000)
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # . . . #
    . # # # .
    `)
```
## Step 2
### Changing Pet's expressions
Change the pictures in the ``||basic.show leds||`` blocks.
```hint
Here:
```
```block
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # # # # #
    . . . . .
    `)
```
```hint
  
And here:
```
```block
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # . . . #
    . # # # .
    `)
```
## Step 3 @showHint
### Create your own mood
Find this place in the code
```blocks
basic.forever(function () {
    while (petmood == 5) {
        basic.showLeds(`
            . . # . .
            . # . # .
            . . . # .
            . . # . .
            . . # . .
            `)
        soundExpression.soaring.playUntilDone()
        basic.pause(2000)
        petmood = randint(1, 4)
    }
})
```
## Step 4 @showHint
### Create your own mood
* [ ]Select a new sound in the ``||music.play sound||`` block.  
* [ ]Change the picture in the ``||basic.show leds||`` block.
```hint
Select sounds here:
```
```block

        soundExpression.soaring.playUntilDone()
```

```hint
  
Change the picture here:
```
```block
basic.showLeds(`
            . . # . .
            . # . # .
            . . . # .
            . . # . .
            . . # . .
            `)
```

## Step 5 @showHint
### Make your pet fall asleep
This task is more complex. You need to modify the code as shown. You'll find all the required blocks in your toolbox. When the new code is assembled, your pet should sometimes go to sleep. Shake your pet to wake it up!
```blocks
basic.forever(function () {
    while (petmood == 5) {
        basic.showString("Zzz...")
        if (input.isGesture(Gesture.Shake)) {
            soundExpression.yawn.playUntilDone()
            basic.pause(2000)
            petmood = randint(1, 4)
        }
    }
})
```

## Step 6
Completed all the tasks? Awesome!
