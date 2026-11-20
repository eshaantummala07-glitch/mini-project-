# Flooder -- Project #28

A colorful tile-filling puzzle game based on **Project #28: "Flooder"**
from *The Big Book of Small Python Projects* by Al Sweigart.

The goal is to make the entire game board one color or shape by
repeatedly changing the tile in the upper-left corner. The selected tile
spreads through adjacent tiles that match the original tile type.

## Features

-   Randomly generated 16 × 14 game board.
-   Six tile types.
-   Color mode and shape mode (for players who find shapes easier to
    distinguish).
-   Recursive flood-fill algorithm.
-   20 moves per game.
-   Win and out-of-moves conditions.
-   Enter `QUIT` to exit during a move prompt.

## Requirements

-   Python 3
-   The `bext` package

## Installation

1.  Make sure Python 3 is installed.

2.  Install the required package:

    ``` bash
    python -m pip install bext
    ```

3.  Download or clone this repository.

## Run the Game

Open a terminal in the project folder and run:

``` bash
python flooder.py
```

When prompted, enter:

-   `Y` to play in shape mode.
-   `N` to play in color mode.

Choose a tile using the letter shown in the prompt. In color mode, the
choices are:

  Key   Color
  ----- --------
  `R`   Red
  `G`   Green
  `B`   Blue
  `Y`   Yellow
  `C`   Cyan
  `P`   Purple

In shape mode, the choices are:

  Key   Shape
  ----- ----------
  `H`   Heart
  `T`   Triangle
  `D`   Diamond
  `B`   Ball
  `C`   Club
  `S`   Spade

Enter `QUIT` when asked to choose a tile to exit the game.

## How to Play

1.  The board is generated with a mixture of six tile types.
2.  The connected group at the upper-left corner is the area you
    control.
3.  Choose a new color or shape.
4.  All connected neighboring tiles that match the previous upper-left
    tile type are changed to your selected type.
5.  Continue choosing tile types to try to make the whole board uniform
    within 20 moves.

## Algorithm: Recursive Flood Fill

The `changeTile()` function performs the flood fill.

-   **Base case:** If the selected tile is already the requested tile
    type, the function returns.
-   **Recursive step:** The current tile is changed, then the function
    checks its left, top, right, and bottom neighbors.
-   A neighbor is processed only if it matches the original tile type.
-   The process continues recursively until the connected region has
    been filled.

The `hasWon()` function checks every board position. It returns `True`
only when all tiles match the tile in the upper-left corner.

## Project Structure

``` text
.
├── flooder.py
└── README.md
```

## Configuration

The game settings can be changed near the beginning of `flooder.py`:

``` python
BOARD_WIDTH = 16
BOARD_HEIGHT = 14
MOVES_PER_GAME = 20
```

Changing these values adjusts the board dimensions and the number of
moves allowed.

## Credits

-   Original project: **Project #28 -- Flooder**
-   Book: *The Big Book of Small Python Projects*
-   Author: **Al Sweigart**
-   Inspired by the **Flood It!** puzzle game.

This implementation is based on the project described in the book. Refer
to the book for its original explanation and source listing.

## License

Add the license that applies to your repository before distributing this
project.
