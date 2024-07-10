#Hunt the Wumpus - README

Overview

Hunt the Wumpus is a text-based adventure game set in a cave with a customizable grid. The player begins in a random empty room, which also serves as the exit to win the game. The goal is to either kill the Wumpus and successfully exit or collect the gold and successfully exit. Various events and obstacles in the cave add challenges and excitement to the gameplay.

Features

Customizable cave grid: Each game features a unique cave grid with different room layouts based on user input.
Events: Rooms can contain stalactites, super bats, gold, or a Wumpus.
Player Actions: Move through rooms, collect gold, and shoot arrows to kill the Wumpus.
Interactive Percepts: Receive hints about nearby events to navigate and make strategic decisions.
Debug Mode: Print the entire grid to assist in testing and debugging.
Game Elements

Wumpus: Can be killed by arrows; moves to a random empty room 75% of the time when it hears an arrow.
Stalactites: 50% chance of killing the player upon entering the room.
Super Bats: Cause the player's movements to be reversed for the next five moves.
Gold: Collect to win the game.
Escape Rope: Represents the starting room and exit point to win the game.
Winning Conditions

Collect the gold and return to the starting room.
Kill the Wumpus and return to the starting room.
Losing Conditions

Being killed by the Wumpus.
Being killed by stalactites.
Assumptions

User inputs are of the correct data type.
Player is playing in normal mode unless specified otherwise.
Classes and Structure

Classes
Event: Parent class for all events (Wumpus, Bats, Stalactites, Gold).
Room: Contains event pointers and player status.
Game: Manages the game grid, player movements, and overall game logic.
Relationships
Event is-a: Wumpus, Bats, Stalactites, Gold.
Game has-a: Grid of Rooms, Player, Wumpus, Bats, Stalactites, Gold.
Key Functions
move_left, move_right, move_up, move_down: Move player in respective directions.
fire_arrow: Shoot an arrow in a specified direction.
check_percepts: Display hints based on adjacent rooms.
player_interact: Trigger specific interactions based on the event in the room.
win_or_lose: Determine if the player has won or lost the game.
User Inputs

Grid size: Length and width of the grid.
Debug mode: True/False to enable or disable debug mode.
Movement: "w" (up), "a" (left), "s" (down), "d" (right).
Arrow firing: "f" to fire an arrow.
Symbols in Grid

Player: *
Wumpus: W
Bats: B
Gold: G
Stalactites: S
Escape Rope: ER
Testing and Debugging

Setup Testing
Print map in debugging mode to verify proper setup.
Check if events are correctly placed in the grid.
Feature Testing
Validate player movement and interactions with events.
Ensure Wumpus behavior on hearing an arrow.
Confirm correct percepts are displayed.
Error Handling
Validate inputs for grid size and movement commands.
Ensure program stability and prevent memory leaks using tools like Valgrind and GDB.

Test Cases:

Input and expected outputs

w	-- Moves up
a -- Moves left
s -- Moves down
d	-- Moves right
W	-- Invalid input
A	-- Invalid input
S	-- Invalid input
D	-- Invalid input
Length input: 3	-- Length is set to 3
Width input: 4	-- Width is set to 4

Compilation and Execution:

Compile the code:
sh
Copy code
make
Run the game:
sh
Copy code
./HuntTheWumpus
Makefile

Future Improvements

Implement a graphical user interface (GUI) for enhanced user experience.
Add more event types and game modes for increased variety.
Introduce difficulty levels to cater to different player skill levels.
