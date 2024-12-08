This web-based game, Plushie Purge, challenges the player to eliminate plushies within a specified time frame. The player must start the game, eliminate plushies, and earn points. When the timer runs out, the game ends and the final score is displayed. The player can choose to restart the game after it ends.

HOW TO PLAY?

https://doll-game.vercel.app/

Go on the above link and click on start game. Once you have started the game, dolls will fall vertically and you have to click on them to kill them. As you click the score will increase and the timer will decrease. After 45 seconds you can check your final score and choose to restart the game again



<img width="412" alt="image" src="https://github.com/user-attachments/assets/af952f2c-0add-43ce-b787-66840656bba4">


<img width="436" alt="image" src="https://github.com/user-attachments/assets/6ca5a2d8-a7d0-44d7-852e-adca57e9222d">


HTML STRUCTURE:

div: This div serves as the main container for all game elements.

  div with header class: Contains the score and timer elements, updated during the game.

  Score:  Displays the current score.

Time: 45</div>: Displays the countdown timer.

 h1 tag: The title of the game displayed at the top of the game screen.

div (id dolls): A container where the dolls will appear (likely dynamically populated via JavaScript).

div(id=endgame): The container that appears when the game ends, showing the final score and the restart button.

  Indicates the end of the game.

<p>Your Score: <span id="finalScore"></span></p>: Displays the final score after the game ends.

<button onclick="restartGame()">Restart</button>: Button that allows the player to restart the game when clicked.

<button id="startButton">Start Game</button>: A button to start the game. This is hidden or disabled until the game starts.

<script src="script.js"></script>: Links to the external JavaScript file that handles the game logic and functionality.

  JAVASCRIPT:The JavaScript code handles the logic of the Plushie Purge game. It provides the functionality for starting the game, creating falling dolls, tracking the score, updating the timer, and handling game-over conditions. It also includes a restart feature 

Global Variables:

score: Tracks the player's current score. Initially set to 0.

gameInterval: The interval ID for the doll generation process (createDoll).

timerInterval: The interval ID for updating the timer (updateTimer).

timeLeft: Stores the remaining time for the game, starting at 45 seconds.

dollsContainer: References the #dolls container element where the dolls appear.

scoreDisplay: References the element (#score) to display the current score.

timerDisplay: References the element (#timer) to display the remaining time.

startButton: References the #startButton element to start the game.

endGameScreen: References the #endGame element to display when the game is over.

finalScoreDisplay: References the element (#finalScore) to display the final score when the game ends.


1. startGame()
    Initializes and starts the game. Resets the score, timer, and game elements.
Resets score to 0 and timeLeft to 45 seconds.
Updates the displayed score and timer.
Clears any existing dolls from the screen by setting dollsContainer.innerHTML to an empty string.
Hides the end game screen by adding the .hidden class.
Disables the start button to prevent multiple game starts.
Starts the game loop by calling createDoll every 500ms and the timer update every second.
2. createDoll()
 Creates a new doll element, assigns a random position, and animates it falling from the top of the screen.
A new div element representing the doll is created.
A random position is assigned using the Math.random() function to determine the horizontal (left) position.
The doll is assigned a random background image from a predefined list of doll URLs.
The doll is appended to the dollsContainer.
The animate() function is used to make the doll fall from the top to the bottom of the screen, with a random fall duration between 2-4 seconds.
An event listener is added to the doll to detect when the user clicks it, increasing the score, creating a blood splatter effect, and removing the doll.
A setTimeout is used to remove the doll after it finishes its fall if it hasn't already been clicked.

3.updateTimer()
Updates the countdown timer and ends the game when the timer reaches zero.
Decreases timeLeft by 1 each second.
Updates the timer display with the new time.
If timeLeft reaches 0, it stops the game by clearing both the gameInterval (doll creation) and timerInterval (timer update).
The game-over screen is revealed by removing the .hidden class from the endGameScreen, and the final score is displayed.
Re-enables the start button to allow the player to restart the game.

4. restartGame()
Restarts the game by calling startGame().
Operation:
Simply calls startGame() to reset the game state and restart the game.

Event Listeners

1. startButton.addEventListener('click', startGame)
Adds an event listener to the start button to trigger the startGame() function when clicked.
Parameters:
'click': Event type.
startGame: The callback function to be executed when the button is clicked.

CSS STRUCTURE:This CSS file defines the visual style and layout for the Plushie Purge game. It provides styling for the body, game container, header, dolls.
