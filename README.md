Tron
====
Background: A good game from a bad movie
-----------------------------------------
Tron was a Disney movie that was released in 1982. It was one of the earliest feature films to reflect the video-game craze of the 1980s. Jeff Bridges stars as a computer programmer who becomes part of the very game that he's programming. The game is a "light cycle duel". Your light cycle races across the arena leaving a trail of laser light behind you. Light cycles can only make 90 degree turns. Touching a laser trail destroys a light cycle, so you try to drive your opponents into a light trail while avoiding the trails yourself. (You can watch the [Tron light cycle scene on YouTube](https://www.youtube.com/watch?v=-BZxGhNdz1k)) There are many examples of the tron game on the internet, one is at [http://www.fltron.com/](http://www.fltron.com/).
 

 
Start with a single player game
-------------------------------
 
1. Start a new program in processing with `setup()` and `draw()` functions.
2. In `setup()` set the background to black. Create a border that is a different color than the background, This border will be the walls that contain the light cycles.
3. Declare and initialize three global variables `x`, `y` and `direction`.
4. In `draw()` write an `if/else` that checks the value stored in `key`.
+ If key means "up", decrement y
+ If key means "down", increment y
+ If key means "left", decrement x
+ If key means "right", increment x
5. The game is over when we cross a light cycle trail. To find out if we are touching the trail, we will use the `get()` function. We will also use `text()` to display a message that the game is over.    
```python
if get(x,y) != color(0,0,0): #if the color at this position isn't black, I ran into something!       
    text("Game Over!",300,200);   
```
6. After the `get()` use the `point()` function to draw a point at the current coordinates.
7. For now, don't use `smooth()` or `strokeWeight()` as this will make the program much more complicated.
At this point you should have a working single player game. You will want the game to end if your trail crosses another trail or goes out of bounds.
 
Then add a computer opponent
----------------------------
1. At this point our `draw()` function is getting big and ugly. Once you get the basic single player tron game working, break it up into functions—put the code that moves the Human player in its own `human()` function.
2. Now we can concentrate on the computer. We need a function similar to `human()`, let’s call it `computer()`. We’ll use `human()` as a basis for `computer()`. What will be the same? different?
3. The computer will need its own variables for its position and direction. The direction variable is similar to key in that it could also be a char but it’s not really a key press, it just stores the direction the computer is traveling
4. The problem now is that the computer never changes direction, We need to add code so that if the computer is about to run into a wall, it will change direction. That means changing the computer direction variable (called `comp` in my program), something like:   
```python
if compDir==UP: #if the computer is traveling up toward the top of the screen        
    compY-=1 #move the computer one pixel up     
if get (compX,compY-1)  != color(0,0,0): #then look one more pixel ahead, am I going to run into something that is not black?      
    compDir=RIGHT  # turn!
```

Extensions:
-----------
If you have extra time you can add more features to the game to make it more interesting. You can make the line thicker by making the dots with `rect()` instead of `point()`, just make sure to move the x and y coordinates by one more than the size of the rectangle. You'll probably want a variable to hold the size of the dot. You can add extra computer opponents or even another human player. You could start the `frameRate` out at a low value, and increase it as the game progresses to make the light cycles move faster the longer you play. Be creative and have fun, your tron game doesn't have to look or work like any other.

Samples of Student Work
-----------------------
