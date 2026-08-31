# Meowze

A cat-themed maze game built with Pygame, originally created as a final project for CS 141 which is Introduction to the Theory of Computation.

## About

Meowze generates a new random maze each playthrough and drops you into it as a cat character, navigating through procedurally generated corridors from entrance to exit.

## Features

- **Procedural maze generation** using Prim's algorithm, producing a new solvable maze layout on every run
- **Sprite-based character animation** via a custom spritesheet handler
- **Custom UI elements** (buttons) for menus and interaction
- **Game state management** to handle different screens (e.g. menu, gameplay)

## How Maze Generation Works

The maze is generated using a randomized version of Prim's algorithm:

1. A grid is initialized as entirely "unvisited."
2. A random starting cell is chosen and marked as a path; its neighboring walls are added to a working wall list.
3. Walls are repeatedly picked at random from that list. If a wall separates a visited cell from exactly one unvisited cell, the unvisited cell is carved into the maze as a path, and its neighboring walls are added to the list.
4. This repeats until no walls remain to process, producing a fully connected, solvable maze.
5. An entrance and exit are carved into the outer boundary once generation completes.

## Project Structure

```
Meowze/
├── main.py           # Entry point / game loop
├── prims.py          # Maze generation logic (Prim's algorithm)
├── button.py          # Custom button UI component
├── spritesheet.py     # Sprite sheet loading/slicing for animation
├── states/            # Game state management (menus, gameplay, etc.)
└── assets/            # Game art and sprites
```

## Requirements

- Python 3.x
- [Pygame](https://www.pygame.org/)

Install dependencies:

```bash
pip install pygame
```

## Running the Game

```bash
python main.py
```

## Notes

- This project was built as a learning exercise, so parts of it (like collision hitbox alignment with sprites) are functional but not pixel-perfect.
- Maze generation occasionally required debugging to ensure walls/cells stayed in bounds and produced a valid, connected maze — see `prims.py` for the core algorithm.

## Course Context

Built for CS 141 as a final project.
