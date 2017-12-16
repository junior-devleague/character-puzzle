# character-puzzle

Can you guess the right character? Create a character puzzle!

![Final Product Example](https://github.com/junior-devleague/character-puzzle/blob/master/assets/example.png)

## Objective

Use **JavaScript Math Methods**, **Append Child**, **Functions**, and more to generate a character guessing game for anyone to play!

## Prerequisites

To complete this project, students should have the following:
* Basic understanding of HTML structures and attributes.
* Basic understanding of Flexbox.
* Intermediate understanding of JavaScript and DOM (Math Methods, Append Child, Functions)

## Your Challenge

### Part I

To complete Part I, fulfill the following requirements:
1. Set up your project file structure through the command line.
2. Create the following:
* HTML file
* CSS file
* JS file
3. Link all of your files correctly.

### Part II HTML

To complete Part II, fulfill the following requirements:

1. Create a ```div``` with an ```id``` of "container".
  2. **Inside** of this div, create another ```div``` with an ```id``` of "guess".
    3. **Inside** of this div, create an ```input``` with an ```id``` of "input".

That's it!

### Part III CSS

1. Target the ```body``` element.
* Set the margin to 0.

2. Target the ```id``` of "container".
* Set the width to the full view width.
* Set the height to the full view height.
* Set the background-image to the path to the mario image in the assets folder or another image of your choice.

3. Target the ```class``` of "piece".
* Set the background-color to white.
* Set the position to the *type of position relative to the viewport, meaning it will always stay in the same place even if the page is scrolled - https://www.w3schools.com/css/css_positioning.asp*.

4. Target the ```id``` of "input".
* Set the width to 200px.
* Set the height to 50px.
* Set the border-radius to 100px. *This makes it slightly round. 200px is like a full circle.*
* Set the font-size to 20px.
* Set the position to the *type of position relative to the viewport, meaning it will always stay in the same place even if the page is scrolled.*
* Set the top property to 20px.
* Set the left property to 20px.
* Set the z-index to 2 so that it is above everything else.

*To get rid of the blue border on the input, you can target the id of input during its focused state, then set the property outline to none.*

### Part IV JS

To complete Part IV, fulfill the following requirements:

1. Create a window.onload function as follows:

``` javascript
window.onload = function() {
  //code goes in here
}

```

2. Create a variable called container that will store your container element.

3. Create a variable called input that will store your input element.

4. Create a variable called array that will hold an empty array.

5. Create a function called generateRandNum that will return a random number between 1 and 200.

6. Create a function called generateRandLeft that will return a random number between 1 and ```document.body.scrollWidth```.

7. Create a function called generateRandTop that will return a random number between 1 and ```document.body.scrollHeight```.

8. Create a function called generatePieces. In this function, do the following:
* Create a variable called numPieces and set that equal to a random number between 1 and 500.
* Create a for loop that will loop through numPieces. In this for loop, do the following:
  * Create a variable called piece that will store a **newly created** div element.
  * Give this new piece a className "piece" like this example:

  ``` JavaScript
  element.className+= "className";
  ```
  * Set the height of the piece to a random pixel number using generateRandNum(). Look at the example below to see how to change styles in CSS!

  ``` javascript
    element.style.property = "value";
  ```

  * Set the width of the piece to a random pixel number using generateRandNum().

  * Set the left property of the piece to a random left location using generateRandLeft().

  * Set the top property of the piece to a random top location using generateRandTop().

  * Append the newly created div stored in the piece variable to the container.

  * Push the newly created div stored in the piece variable to the arr array.

9. Create a function called takeAwayPiece. In this function, do the following:
  * Create a variable called randNumArray and set that equal to a random number between 1 and the length of the arr array.
  * Access a random element from the arr array using randNumArray. Set the display CSS property of this element to "none".

10. Create a variable called interval. Set that equal to a ```setInterval``` that will take in a **reference** to the function takeAwayPiece and execute the function every 2 seconds.

11. Create an ```Event Listener``` to the window that detects for a 'keypress' with the event as parameter in the function. In this Event Listener, do the following:
  * Create an **if statement** that will check if the event.keyCode is equal to 13, and if the value of the input is *not equal to* nothing.
    * **Inside of this if statement**, create another **if statement** that will check if the value of the input is the correct character name. ("mario" if you chose to use the mario background asset).
      * If it is true, clear the interval!
      * Alert the player that they've won!

12. Invoke the function generatePieces().

## Stretch Goals

1. Keep the game going! After the user has successfully, done the first puzzle, give them another one! After the user has successfully finished the first puzzle:
  1. Set the container's background-image property to another image.
  2. Call the generatePieces function to generate pieces.
  3. Reset the interval.  
  4. Check if the input is the correct answer!

*Hint: You may want to use objects to help organize this as follows:*

``` javascript
var puzzle1 {
  image: 'pathtoimage',
  solution: 'mario'
}
```

BONUS: Create a function for the object that does all the checking!  

2. Create a points variable that will store points starting with 100. Every time a piece has disappeared, decrease the points by 1! Show the user their points on the page.
