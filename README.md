# snakes-and-ladder
 Design a Snakes and Ladder game that follows SOLID principles and OOAD concepts.


TODO:
Learn how to implement the mentioned design patterns in C#:
Create a C# project (console application)
Add singleton pattern and bootstrapper

Ground rules:
singleton design pattern
dependecy injection
bootstrapper - <Interface, Class>
Interact based on interfaces

Additional inputs/comments:
Multiple difficulty levels: easy (less snakes, more ladders), medium (equal snakes and ladders), hard (more snakes, less ladders)
Generate snakes and ladders at random at the beginning of game
Make sure every snake and ladder are unique (both start and end) and there is no chaining of actions, infinite loops
Board can be represented by a single number (height, width not needed, can use only height*width)
Can use queue instead of array to track turns and players.
Print statements appropriately to show the status.
Break the game in case only 1 player is left (ranking is generated here instead of only 1 player winning and rest losing)
Run demo simulation and store result for demo purpose


Snake:
    int start
    int tail

Ladder:
    int start
    int tail

IBoard:
    bool IsLastGridInGame(int position)
    int IsBitBySnake(int position)
    int IsBottomOfLadder(int position)

Board:
    height: int
    width: int
    snakes: array[pair<int,int>]
    ladders: array[pair<int,int>]

    private void initBoard()

    bool IsLastGridInGame(location: int)
    int IsBitBySnake(location: int) // if yes, returns new position. if no, returns -1
    int IsBottomOfLadder(location: int) // if yes, returns new position. if no, returns -1

IGame:
    PlayTurn();
    GetCurrentPlayer();
    GetCurrentPositions();

Game(int numberOfPlayers):
    numberOfPlayers: int
    board: Board
    currentPosition: array[int]
    dice: Dice
    currentPlayer: int

    PlayTurn();
    GetCurrentPlayer();
    GetCurrentPositions();
    

IDice(int faces):
    int RollDice()

Dice(int faces):
    int faces;
    int RollDice();

IPlayer()
    GetPlayerID();
    GetPlayerName();
    GetPlayerPersonalDetails();

Player:
    Name: string
    ID: string
    // personal details
    GetPlayerID();
    GetPlayerName();
    GetPlayerPersonalDetails();