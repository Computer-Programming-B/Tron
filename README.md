Tron
====
Background: A good game from a bad movie
-----------------------------------------
Tron was a Disney movie that was released in 1982. It was one of the earliest feature films to reflect the video-game craze of the 1980s. Jeff Bridges stars as a computer programmer who becomes part of the very game that he's programming. The game is a "light cycle duel". Your light cycle races across the arena leaving a trail of laser light behind you. Light cycles can only make 90 degree turns. Touching a laser trail destroys a light cycle, so you try to drive your opponents into a light trail while avoiding the trails yourself. (You can watch the [Tron light cycle scene on YouTube](https://www.youtube.com/watch?v=-BZxGhNdz1k)) There are many examples of the tron game on the internet, one is at [http://www.fltron.com/](http://www.fltron.com/).
 

 
Start with a single player game
-------------------------------
1. You may find slides 23 - 38 of the [Functions, Algorithms and Abstractions presentation](https://docs.google.com/presentation/d/12evLVpEOAdoKxIjuTu3OP5GegrFHFTkJHr4dX1lfEow/edit?usp=sharing) and/or [this video](http://youtu.be/5LaX86RCMuQ?hd=1) helpful in completing the following steps.
2. Move background to `setup()`, declare two variables for `x` and `y` and initialize each to 200. Change the background color to blue, and make a slightly smaller black rectangle inside of it
3. In `draw()` set the `stroke()` to white and then draw a `point()` at (x,y). After that, increase `x` by 1. Run your program. You should see a small white dot in the center of the screen move to the right leaving a trail behind it.
4. Copy the following `notBlack()` function into the bottom of your program. Make sure it not inside the curly braces of another function.
```javascript
function notBlack() {
  let a = get(x, y);
  if (a[0] != 0) return true;
  else if (a[1] != 0) return true;
  else if (a[2] != 0) return true;
  return false;
}
```
5. Declare a `gameOver` variable at the top of your program and intialize it to `false`. 
6. Add an `if` statement to check if `notBlack()` is `true`. If so, display a "GAME OVER" message. and set `gameOver` to `true`.
7. Add another `if` statement about the previous one. If `gameOver` is `true`, then `return;`
8. Replace the code in `draw()` that makes `x` one bigger with four `if` statmeents
+ If `direction` is 37, make `x` smaller by 1 
+ If `direction` is 38, make `y` smaller by 1 
+ If `direction` is 39, make `x` bigger by 1
+ If `direction` is 40, make `y `bigger by 1 
9. Add a `function keyPressed()` that changes `direction` to match `keyCode`.
+ If `keyCode` is 37, set `direction` to 37
+ If keyCode` is 38, set `direction` to 38
+ If keyCode` is 39, set `direction` to 39
+ If keyCode` is 40, set `direction` to 40
10. Run the program. Once a person clicks on the screen, the light cycle should now be able to turn with the arrow keys
11. Add a 'mousePressed` function that increases `direction` by 1 with a right click and decreases it by 1 with a left click.
12. At this point you should have a working single player game. You should be able to operate the light cycle with either the keyboard or mouse


 
Then add a computer opponent
----------------------------
You may find slides 374 - 386 of the PythonProcessing PowerPoint helpful in adding a computer opponent.
1. At this point our `draw()` function is getting big and ugly. Once you get the basic single player tron game working, break it up into functions—put the code that moves the Human player in its own `human()` function.
2. Now we can concentrate on the computer. We need a function similar to `human()`, let’s call it `computer()`. We’ll use `human()` as a basis for `computer()`. What will be the same? different?
3. The computer will need its own variables for its position and direction. The direction variable is similar to key in that it could also be a char but it’s not really a key press, it just stores the direction the computer is traveling
4. The problem now is that the computer never changes direction, We need to add code so that if the computer is about to run into a wall, it will change direction. That means changing the computer direction variable (called `compDir` in my program), something like:   
```python
if(compDir == RIGHT):                   # if the computer is moving right
   compX = compX + 1                    # move the computer one pixel right
   if(get(compX+1,compY) != color(0)):  # then look one pixel ahead, will I run into something that isn't black?
      compDir = DOWN                    # turn!
```

Extensions:
-----------
Your tron game doesn't have to look or work like any other. Possible extensions are:
+ Added graphics for collisions
+ A timer that increase the score the longer the player avoids crashing
+ A two player game where one person uses the mouse and the other uses the keyboard
+ A computer opponent

Samples of Student Work 
-----------------------
#### (use the left and right mouse buttons to control the light cycle)   
[Marc](https://trinket.io/embed/python/df5a0e966e?outputOnly=true&runOption=run&start=result)   
