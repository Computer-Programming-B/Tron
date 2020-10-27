Tron
====   

![](TronLighCycles.JPG)   

Background: A good game from a bad movie
-----------------------------------------
Tron was a Disney movie that was released in 1982. It was one of the earliest feature films to reflect the video-game craze of the 1980s. Jeff Bridges stars as a computer programmer who becomes part of the very game that he's programming. The game is a "light cycle duel". Your light cycle races across the arena leaving a trail of laser light behind you. Light cycles can only make 90 degree turns. Touching a laser trail destroys a light cycle, so you try to drive your opponents into a light trail while avoiding the trails yourself. You can watch the original [Tron light cycle scene on YouTube](https://www.youtube.com/watch?v=1kyiQzc4134). There are many examples of the tron light cycle game on the internet, one is at [http://www.fltron.com/](http://www.fltron.com/). We'll use the turtle graphics in Python 3 to create the graphics in this assignment. You may also find slides 112-131 in the [slide presentation](https://docs.google.com/presentation/d/1rICcmNbnGYsB-cV_6EatPyzcOS2sId80Jh2kayUzm4Q/edit?usp=sharing) helpful.
 

 
Suggested steps for starting with a single player game
-------------------------------
1. Set up an infinite loop that moves the turtle forward. Something like this:   
   ```python
   from turtle import *
   
   pen(pensize=3) #make line thickness 3
   
   while True:
       forward(1)
   ```
2. Now we need to have the program "listen" for the left and right arrow keys. Add `listen()` above the `while` loop   
3. Since light cycles can only turn by 90° we'll define two functions that can turn the turtle left or right by 90°. Here's the function for left. Define it above the `while` loop:   
   ```python
   def goLeft():
      left(90)
   ```
4. Now we will "bind" the left and right arrow keys to the functions that we just defined. Here's the code that binds the `goLeft` function to the `"Left"` arrow key:   
   ```python
   onkey(goLeft,"Left")
   ```
5. At this point you should have a working single player game. You should be able to operate the light cycle with either the keyboard or mouse. 
6. Now we'll store the (x,y) coordinates of the light cycle as a tuple in a list
7. We can check for a collision with our light cycle trail by checking to see if our current position is already in the list

Extensions:
-----------
Once you get the basic single player game working, you can start adding other features. Your tron game doesn't have to look or work like any other, have fun and be creative! Possible extensions inlcude:
+ Add walls to make the tron light cycle arena
+ Added graphics for collisions
+ Added obstacles or a maze to make the game more challenging
+ A timer that increases the score the longer the player avoids crashing
+ The ability to restart the game
+ Turbo mode and/or power ups to move the light cycle faster
+ Self driving mode where like a self driving car the light cycle automatically avoids obstacles 
+ A two player game
+ A computer opponent (or even multiple computer opponents for real craziness!)

Samples of Student Work 
-----------------------
None yet!
