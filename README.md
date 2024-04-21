# project-game


iteration 0: Getting Started
The first thing we will do is get familiar with the starter code provided for the exercise:

Open the index.html file and take a look at the HTML structure of the game. The div game-intro, game-container, and game-end represent the screens of the game.

Open the styles/style.css file and take a look at the CSS styles for the game. The styles are already provided, but you are free to make changes to the styles or animations to your liking during the exercise.

The starter code includes a couple of JavaScript files that are located in the js folder:

script.js - This file contains code that handles the game's start button. Please open it and take a look at how the event listener is set up.

game.js - This is the file where we will define the Game class to represent the game's data (properties) and behaviors (methods). We will fill out this class as we progress through the exercise.



Iteration 1: Create the Game
In this iteration, you will create the Game class in the js/game.js file. This class will be responsible for managing the game data and behavior.

The class Game is defined in the js/game.js file.

The Game class should have the following properties defined in the constructor:

startScreen - holds the div element #game-intro. To access the element, use either document.getElementById() or document.querySelector().

gameScreen - holds the div element #game-screen.

gameEndScreen - holds the div element #game-end.

player - leave it as null for now. We will use this property to save the instance of the Player class that we'll create it in the next iteration.

height - the height of the game screen in pixels. We will set it to 600.

width - the width of the game screen in pixels. We will set it to 500.

obstacles - an empty array. We'll use it to store the obstacle instances we create later.

score - a score increases every time an obstacle is passed. Set its initial value to 0.

lives - the number of remaining lives the player has. Set its initial value to 3.

gameIsOver - a flag used to track whether the game is over. Set the initial value to false.

gameIntervalId - a variable used to store the id of the interval running the game loop. We store and use this id to clear the interval once the game is over.

gameLoopFrecuency - a number that indicates the interval in milliseconds at which the game loop will execute. A good value for most screens is 1000/60, which equates to the the game being updated every ~17 millisecond, or about 60 times per second (60fps).




The Game class should have the following methods:

start()
gameLoop()
update()


iteration 2: Start the Game
Check the provided code in the js/script.js file. When the Start Game button is clicked, inside the startGame function we should create a new instance of the Game class and start the game by invoking the start() method:



Iteration 3: Create the Player
In this iteration, we will create the Player class, representing the player's car.

Open the js/ folder and create a new file called player.js.

In the index.html file, add a script tag to link the player.js file.

Inside the player.js file that you just created, define a new class called Player.

The Player class should have the following properties defined in the constructor:

gameScreen - the game screen element passed as an argument to the constructor.

left - the horizontal position of the car passed as an argument to the constructor.

top - the vertical position of the car passed as an argument to the constructor.

width - the width of the car element passed as an argument to the constructor.

height - the height of the car element passed as an argument to the constructor.

directionX - initially set to 0. It is used to specify the horizontal movement direction and can have the following values:

0: not moving horizontally
1: moving horizontally to the right
-1: moving horizontally to the left
directionY - initially set to 0. It is used to specify the vertical movement direction and can have the following values:

0: not moving vertically
1: moving vertically down
-1: moving vertically up
element - the image element representing the car. This image element should be created in the constructor using the provided image source (image url) passed as an argument to the constructor.


In order to set the exact position of the player element on the game screen, it should be positioned absolutely (position: absolute). The exact position is determined by this element's width, height, left and top properties.

Make sure to append the newly created element to the gameScreen.

The Player class should have the following methods:

move()
updatePosition()
didCollide(obstacle)

You can use the below example of the completed code as a reference:

See the code

Iteration 4: Add the Player to the Game
As a reminder, we have already defined the player property of the Game class and set it to null. Now let's instantiate a new Player object and store it in the player property of the Game.
See the code

To continuously update the player's position during gameplay, add a call to the player.move() method within the update() method of the Game class.
See




Iteration 5: Handle Keyboard Input
The goal of this iteration is to allow the player to control the car using the keyboard.

To do this, we will add an event listener in the js/script.js file, which will update the player's car directionX and directionY properties based on the keys that the user presses on the keyboard. This function listens for the keydown event using document.onkeydown and checks if the pressed key matches any of the allowed keystrokes (arrow keys).





Iteration 6: Obstacles
In this iteration, we will create the Obstacle class, which will be used to create obstacle instances.

Open the js/ folder and create a new file called obstacle.js.

In the index.html file, add a script tag to link the new obstacle.js file.

Inside the obstacle.js file that you just created, define a new class called Obstacle.

The Obstacle class should have the following properties defined in the constructor:

gameScreen - the game screen element passed as an argument to the constructor.

left - randomly generated number representing the horizontal position of the car.

top - the initial vertical position of the obstacle. We will set it to 0.

width - the width of the obstacle element. We will set it to 100.

height - the height of the obstacle element. We will set it to 150.

element - the image element that represents the obstacle car. We will use the image of the red car available in the images/ folder.

Iteration 6: Obstacles
In this iteration, we will create the Obstacle class, which will be used to create obstacle instances.

Open the js/ folder and create a new file called obstacle.js.

In the index.html file, add a script tag to link the new obstacle.js file.

Inside the obstacle.js file that you just created, define a new class called Obstacle.

The Obstacle class should have the following properties defined in the constructor:

gameScreen - the game screen element passed as an argument to the constructor.

left - randomly generated number representing the horizontal position of the car.

top - the initial vertical position of the obstacle. We will set it to 0.

width - the width of the obstacle element. We will set it to 100.

height - the height of the obstacle element. We will set it to 150.

element - the image element that represents the obstacle car. We will use the image of the red car available in the images/ folder.

Iteration 6: Obstacles
In this iteration, we will create the Obstacle class, which will be used to create obstacle instances.

Open the js/ folder and create a new file called obstacle.js.

In the index.html file, add a script tag to link the new obstacle.js file.

Inside the obstacle.js file that you just created, define a new class called Obstacle.

The Obstacle class should have the following properties defined in the constructor:

gameScreen - the game screen element passed as an argument to the constructor.

left - randomly generated number representing the horizontal position of the car.

top - the initial vertical position of the obstacle. We will set it to 0.

width - the width of the obstacle element. We will set it to 100.

height - the height of the obstacle element. We will set it to 150.

element - the image element that represents the obstacle car. We will use the image of the red car available in the images/ folder.

Once you create the obstacle element, you should position it absolutely (position: absolute) to be able to specify its exact position. The exact position is determined by this element's width, height, left and top properties.

Also, remember to append the obstacle element to the gameScreen.

The Obstacle class should have the following methods:

move()
updatePosition()

teration 7: Handling Collisions
The last key aspect of the game is handling the collisions between the player's car and the obstacle cars and generating obstacles randomly.

To do this, you need to modify the update() method in the Game class to do the following:

Game - update()
This method is responsible for updating the game state during each loop iteration. Here are the steps that it should perform:

Update player's car position based on its directionX and directionY properties by invoking the method player.move().

Randomly generate a new obstacle.

Iterate through the list of obstacles, move each obstacle, and check for collision with the player’s car.

If there is a collision, remove the obstacle from the game and reduce the player’s remaining lives by one.

If the obstacle is off the screen, remove the obstacle from the game and increase the player’s score by one.

Check if the player has run out of lives, and end the game if so. Create a new method (endGame) responsible for ending the game.

endGame()
Remove a player and all the obstacles from the DOM.
Set the gameIsOver flag to true.
Hide the game screen.
Show the end game screen.


Iteration 8: End Game Screen
In this final iteration, we will implement the end game screen, shown to the user when the game is over.

Check the code in the js/script.js. We will do this by adding a click event listener to the Restart Game button. The handler function for this listener should reload the page when the button is clicked. You can achieve this by using the location.reload() method.


You can refer to the example of the completed code below to guide you through this iteration:

See the code

// js/script.js

window.onload = function () {
  // ...

  // Add an event listener to the restart button
  restartButton.addEventListener("click", function () {
    // Call the restartGame function when the button is clicked
    restartGame();
  });

  // The function that reloads the page to start a new game
  function restartGame() {
    location.reload();
  }
};



added adiditional element.







