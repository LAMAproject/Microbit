# Microbit
Computer Science Project: By: Lara Lotz and Emma Kent  

Program description: This project is a basic fit bit counter that counts your steps as you walk. Every time you walk a smiley face appears on the microbit and after the Fitbit has reached 10 steps it plays music. When an amount of steps is reached, the microbit will play music to "congratulate" and encourage the person walking..  To see the number of steps you have done you must click button A and it will show you the exact amount of steps taken.   

BBC microbit sensors/characteristics used: Music- music was used when a certain amount of steps are reached to "congratulate" the person walking. Buttons- a button was used to check the amount of steps taken. Gesture/Animation - A specific face is shown when an amount of steps is reached. Movement- If the microbit is "shaken", a step is added to a counter and and the steps are counted.

Testing information: To test the microbit we shook it until the 10 steps were reached to see if the sound and the face would appear. However, in the beginning we were faced with a few problems. For example, the amount of steps taken wouldn't appear on the lights when button A was pressed.  We eventually figured out that it was an indentation error and we were using an If statement instead of a while statement. We also had to figure out how to change the face when 10 steps were reached, which was challenging as the microbit would show a smiley face, as well as, the silly face. As a result, we had to change our code in order to stop the smiley face from appearing. Overall, it was a challenging yet fun project.  

Ideas to extend the project: A possible add-on could be to program the microbit to tell the difference between a person running and walking. This could be done by using an if statement and the variable running_time(). 

```
from microbit import *
import speech
import music
steps = 0

while True:
    # Check to see if a step has been taken. If so, display a smile
    #and increase the number of steps by 1
    if accelerometer.was_gesture('shake'):
        steps += 1
        display.show(Image.HAPPY)
        sleep(500)
        display.clear()
        
         # When reaches 10 steps,makes a noise
        if steps>9 and steps<11:
             music.play(music.ENTERTAINER)
             display.show(Image.SAD)
             sleep(500)
             display.clear()

        if steps>99 and steps<101:
             music.play(music.NYAN)
             display.show(Image.SILLY)
             sleep(500)
             display.clear()

    # Check to see if button A has been pressed. If so, display the number of steps taken
    if button_a.is_pressed():
        string_steps = str(steps)
        display.show(string_steps)
        sleep(500)
        display.clear()
```

![alt text](https://github.com/LAMAproject/Microbit/blob/master/IMG_20190906_092726_BURST001_COVER.jpg "The microbit "fit bit" when a person isn't walking.")
![alt text](https://github.com/LAMAproject/Microbit/blob/master/IMG_20190906_092820_BURST001_COVER.jpg "The step counter that shows the amount of steps taken,when button a is pressed")
![alt text](https://github.com/LAMAproject/Microbit/blob/master/IMG_20190906_095553.jpg "The microbit when connected to a battery. This means that the fit bit can be portable.")
![alt text](https://github.com/LAMAproject/Microbit/blob/master/IMG_20190906_095702_BURST001_COVER.jpg "The microbit when a person walks.(A specific face will be shown depending on the amount of steps taken. a step is added to the counter.")
