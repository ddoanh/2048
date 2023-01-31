# 2048

## Description:
- The game is played on a grid of squares, each of which can either be empty or contain a tile bearing an integer–a power of 2 greater than or equal to 2. Before the first move, the application adds a tile containing either 2 or 4 to a random square on the initially empty board. The choice of 2 or 4 is random, with a 75% chance of choosing 2 and a 25% chance of choosing 4.
- The player then chooses a direction via their arrow keys to tilt the board: north, south, east, or west. All tiles slide in that direction until there is no empty space left in the direction of motion (there might not be any to start with). A tile can possibly merge with another tile which earns the player points.

![example-2048](https://user-images.githubusercontent.com/98563830/215855210-4e0b52b3-d787-4524-b9c6-eb8cb62fcc28.gif)
## Rules:
1. Two tiles of the same value merge into one tile containing double the initial number.
2. A tile that is the result of a merge will not merge again on that tilt. For example, if we have [X, 2, 2, 4], where X represents an empty space, and we move the tiles to the left, we should end up with [4, 4, X, X], not [8, X, X, X]. This is because the leftmost 4 was already part of a merge so should not merge again.
3. When three adjacent tiles in the direction of motion have the same number, then the leading two tiles in the direction of motion merge, and the trailing tile does not. For example, if we have [X, 2, 2, 2] and move tiles left, we should end up with [4, 2, X, X] not [2, 4, X, X].

## The MVC pattern:
1. The model represents the subject matter being represented and acted upon – in this case incorporating the state of a board game and the rules by which it may be modified. Our model resides in the Model, Side, Board, and Tile classes. The instance variables of Model fully determine what the state of the game is. Note: You’ll only be modifying the Model class.
2. A view of the model, which displays the game state to the user. Our view resides in the GUI and BoardWidget classes.
3. A controller for the game, which translates user actions into operations on the model. Our controller resides mainly in the Game class, although it also uses the GUI class to read keystrokes.
