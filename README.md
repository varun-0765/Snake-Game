## Snake Game

### Overview
This project is a straightforward, terminal-based Snake game built in C. It showcases fundamental game development principles, including a game loop, real-time input handling, collision detection, and dynamic state management. The game runs in a text interface, where the snake, food, and boundaries are represented using simple characters.

### Features
#### Game Initialization:
- The game starts by setting up the snake’s initial position and randomly placing a food item on the board.
- The snake appears at the center of the play area, while the food is positioned randomly.

#### Game Rendering:
- A `Draw()` function is used to display the game board.
- The board includes upper and lower boundaries, side walls, the snake’s head (denoted by 'O'), body segments (represented by 'o'), and food (shown as 'F').

#### User Input:
- Real-time keyboard input is managed using `_kbhit()` and `_getch()` from `conio.h`.
- Controls:
  - 'a' moves the snake left.
  - 'd' moves the snake right.
  - 'w' moves the snake up.
  - 's' moves the snake down.
  - 'x' exits the game.

#### Game Mechanics:
- The snake’s movement is updated according to user input, with its body following its head.
- The game implements boundary wrap-around, allowing the snake to re-enter from the opposite side upon reaching the edge.
- Collision detection checks whether the snake collides with itself or consumes food.

#### Scoring System:
- Eating food increases the player’s score by 10 points.
- Each time food is consumed, the snake grows in length, increasing difficulty.

#### Game Loop:
- The `main()` function continuously runs the game until a game-over condition occurs.
- In each iteration:
  - The screen is cleared and redrawn.
  - User input is processed.
  - Game mechanics are updated.
  - A short delay (`Sleep()`) is introduced to regulate speed.

### Step-by-Step Breakdown
#### Initialization (`Setup()`):
- The snake is placed in the middle of the board.
- A food item is randomly positioned using `rand() % WIDTH` and `rand() % HEIGHT`.
- The score is set to zero at the start.

#### Rendering (`Draw()`):
- The screen is refreshed with `system("cls")` to keep the visuals updated.
- The top and bottom borders are drawn.
- Each row of the board:
  - Begins with a left border.
  - Displays the snake’s head, food, body segments, or empty spaces as needed.
  - Ends with a right border.
- The bottom border and score display are updated.

#### Handling Input (`Input()`):
- Detects key presses using `_kbhit()`.
- Changes the snake’s direction based on user input or exits the game if 'x' is pressed.

#### Game Logic (`Logic()`):
- Updates the snake’s body by shifting previous positions.
- Moves the snake’s head in the chosen direction.
- Implements wrap-around for movement beyond the board’s boundaries.
- Checks for self-collision to determine if the game is over.
- Detects food consumption, increases the score, and extends the snake’s length.

#### Main Loop (`main()`):
- The game starts with `Setup()`.
- A continuous loop (`while (!gameOver)`) performs the following:
  - Draws the game board.
  - Captures and processes input.
  - Updates game logic.
  - Regulates speed with `Sleep(10)`.
- Once the game ends, the final score is displayed.

