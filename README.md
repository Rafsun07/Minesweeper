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

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. Ensure that your code follows the project's coding standards and includes appropriate tests.


## Contact

For questions, suggestions, or issues, please open an issue on GitHub or contact me at [rafsun.eram@gmail.com](mailto:rafsun.eram@gmail.com).

## Acknowledgements

- Inspired by the classic Minesweeper game.
- Developed using Python.

---
