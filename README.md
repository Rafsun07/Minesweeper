# Minesweeper Game

A Python implementation of the classic Minesweeper game. This project allows users to create a Minesweeper board, dig at specific locations, and uncover cells until all safe cells are revealed or a bomb is dug.

## Features

- Customizable board size and number of bombs.
- Recursive digging to uncover safe areas.
- Displays the current state of the board after each move.
- End game messages for both victory and game over scenarios.

## Installation

1. **Clone the repository:**

    ```
    git clone https://github.com/Rafsun07/minesweeper.git
    cd minesweeper
    ```

2. **Run the game:**

    ```
    python minesweeper.py
    ```

## Usage

1. **Start the game:** Run the `minesweeper.py` script.
2. **Input dig locations:** When prompted, enter the row and column where you want to dig in the format `row,col`. For example: `0,3`.
3. **Game Over:** If you dig a bomb, the game will reveal the entire board and end.
4. **Victory:** Uncover all safe cells to win the game.

## Example

Here's an example of how the game runs:

1. **Starting the game:**
    ```
    python minesweeper.py
    ```

2. **Initial board state:**

    ```
       0  1  2  3  4  5  6  7  8  9  
    -----------------------------------
    0 |    |    |    |    |    |    |    |    |    |    |
    1 |    |    |    |    |    |    |    |    |    |    |
    2 |    |    |    |    |    |    |    |    |    |    |
    3 |    |    |    |    |    |    |    |    |    |    |
    4 |    |    |    |    |    |    |    |    |    |    |
    5 |    |    |    |    |    |    |    |    |    |    |
    6 |    |    |    |    |    |    |    |    |    |    |
    7 |    |    |    |    |    |    |    |    |    |    |
    8 |    |    |    |    |    |    |    |    |    |    |
    9 |    |    |    |    |    |    |    |    |    |    |
    -----------------------------------
    ```

3. **Digging at (0,3):**

    ```
    Where would you like to dig? Input as row,col: 0,3
       0  1  2  3  4  5  6  7  8  9  
    -----------------------------------
    0 |    |    |    |  1 |    |    |    |    |    |    |
    1 |    |    |    |    |    |    |    |    |    |    |
    2 |    |    |    |    |    |    |    |    |    |    |
    3 |    |    |    |    |    |    |    |    |    |    |
    4 |    |    |    |    |    |    |    |    |    |    |
    5 |    |    |    |    |    |    |    |    |    |    |
    6 |    |    |    |    |    |    |    |    |    |    |
    7 |    |    |    |    |    |    |    |    |    |    |
    8 |    |    |    |    |    |    |    |    |    |    |
    9 |    |    |    |    |    |    |    |    |    |    |
    -----------------------------------
    ```

4. **Continuing the game, digging at (1,1):**

    ```
    Where would you like to dig? Input as row,col: 1,1
       0  1  2  3  4  5  6  7  8  9  
    -----------------------------------
    0 |    |    |    |  1 |    |    |    |    |    |    |
    1 |    |  1 |    |    |    |    |    |    |    |    |
    2 |    |    |    |    |    |    |    |    |    |    |
    3 |    |    |    |    |    |    |    |    |    |    |
    4 |    |    |    |    |    |    |    |    |    |    |
    5 |    |    |    |    |    |    |    |    |    |    |
    6 |    |    |    |    |    |    |    |    |    |    |
    7 |    |    |    |    |    |    |    |    |    |    |
    8 |    |    |    |    |    |    |    |    |    |    |
    9 |    |    |    |    |    |    |    |    |    |    |
    -----------------------------------
    ```

5. **Game over by digging at (0,0):**

    ```
    Where would you like to dig? Input as row,col: 0,0
    SORRY GAME OVER :(
       0  1  2  3  4  5  6  7  8  9  
    -----------------------------------
    0 |  * |  1 |    |  1 |    |    |    |    |    |    |
    1 |    |  1 |    |    |    |    |    |    |    |    |
    2 |    |    |    |    |    |    |    |    |    |    |
    3 |    |    |    |    |    |    |    |    |    |    |
    4 |    |    |    |    |    |    |    |    |    |    |
    5 |    |    |    |    |    |    |    |    |    |    |
    6 |    |    |    |    |    |    |    |    |    |    |
    7 |    |    |    |    |    |    |    |    |    |    |
    8 |    |    |    |    |    |    |    |    |    |    |
    9 |    |    |    |    |    |    |    |    |    |    |
    -----------------------------------
    ```
    
## How The Code Works:

### Overview
The code defines a Minesweeper game that can be played in the command line. It includes a `Board` class to represent the game board and a `play` function to manage the game loop. Here’s a detailed breakdown of each part:

### Board Class

**`__init__` Method:**

- Parameters: `dim_size` (dimension of the board), `num_bombs` (number of bombs).
- Purpose: Initializes the board with the given dimensions and number of bombs. It calls helper methods to create the board and assign values.
- Key Variables:
    - `self.dim_size`: Size of the board (number of rows/columns).
    - `self.num_bombs`: Number of bombs on the board.
    - `self.board`: 2D list representing the game board.
    - `self.dug`: Set to keep track of the locations that have been dug.

**`make_new_board` Method:**

- Purpose: Creates a new game board with the specified number of bombs placed randomly.
- Process:
    - Initializes a 2D list filled with `None` to represent the board.
    - Randomly places bombs (`'*'`) on the board until the specified number is reached.

**`assign_values_to_board` Method:**

- Purpose: Assigns a number to each non-bomb cell representing how many bombs are adjacent to it.
- Process:
    - Iterates through each cell on the board.
    - For each non-bomb cell, calculates the number of neighboring bombs using `get_num_neighboring_bombs`.

**`get_num_neighboring_bombs` Method:**

- Purpose: Counts the number of bombs adjacent to a given cell.
- Parameters: `row`, `col` (position of the cell).
- Process:
    - Checks the surrounding cells (including diagonals).
    - Ensures it doesn't go out of bounds.
    - Returns the count of bombs found.

**`dig` Method:**

- Purpose: Digs at a specified location on the board.
- Parameters: `row`, `col` (position to dig).
- Process:
    - Adds the position to the `dug` set.
    - If the cell contains a bomb (`'*'`), returns `False` indicating the game is over.
    - If the cell has neighboring bombs, returns `True`.
    - If the cell has no neighboring bombs, recursively digs adjacent cells.

**`__str__` Method:**

- Purpose: Provides a string representation of the board for display.
- Process:
    - Creates a new 2D list representing what the user would see.
    - Shows dug cells with their values and hides undug cells.
    - Formats the board as a string with row and column indices for easy reading.


**`play` Function:**

- Purpose: Manages the game loop, handling user input and game progression.
- Process
    - Initialize Board:
        - Creates a `Board` object with the specified dimensions and number of bombs.
    - Game Loop:
        - Repeats until all non-bomb locations are dug or a bomb is hit.
        - Displays the current state of the board.
        - Prompts the user for a location to dig (`row,col`).
        - Validates the input to ensure it’s within the board's bounds.
        - Calls the `dig` method on the board.
        - If a bomb is hit (`dig` returns `False`), the game ends.
        - If all safe spots are dug, the player wins.

    - End Game:
        - Displays a victory message if all safe spots are dug.
        - Displays a game over message if a bomb is hit and reveals the entire board.

## Summary

- The `Board` class manages the game board, including bomb placement and calculating neighboring bomb counts.
- The `play` function handles user interaction and the main game loop.
- The game ends either when the player digs up a bomb or when all safe spots are uncovered.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. Ensure that your code follows the project's coding standards and includes appropriate tests.


## Contact

For questions, suggestions, or issues, please open an issue on GitHub or contact me at [rafsun.eram@gmail.com](mailto:rafsun.eram@gmail.com).

## Acknowledgements

- Inspired by the classic Minesweeper game.
- Developed using Python.

---
