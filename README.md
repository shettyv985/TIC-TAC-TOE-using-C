# TIC-TAC-TOE-using-C

Certainly, here's a concise explanation for every single line of the code:

```c
#include <stdio.h>
#include <stdlib.h>
```
Standard library headers.

```c
char square[10] = {'o','1','2','3','4','5','6','7','8','9'};
```
Array to represent the Tic Tac Toe board.

```c
int checkWin();
void drawBoard();
```
Function prototypes.

```c
int main(){
```
Start of the main function.

```c
int player = 1, i, choice;
char mark;
```
Player tracking and variables.

```c
do {
    drawBoard();
    player = (player % 2) ? 1 : 2;
    printf("Player %d, enter the choice : ",player);
    scanf("%d",&choice);
    mark = (player == 1) ? 'X' : 'O';
    // Player's choice logic
    i = checkWin();
    player++;	
} while(i == -1);
// Game loop until a result is obtained

drawBoard();
if(i==1){
    printf("==>Player %d won\n",--player);
}
else {
    printf("==>Game draw");
}
```
Game loop and result announcement.

```c
int checkWin(){
    // Win-check logic
}

void drawBoard(){
    system("cls");
    // Display the game board
}
```
Functions for checking win conditions and displaying the game board.

```c
return 0;
}
```
Certainly! This `checkWin()` function is responsible for determining the game's outcome by checking the Tic Tac Toe board for winning or draw conditions. Here's a step-by-step explanation:

1. The function starts with an `if-else if` chain, checking for different combinations of squares that could result in a win for any player:

```c
if(square[1] == square[2] && square[2] == square[3])
    return 1;
```

This line checks if all three squares in the top row have the same mark ('X' or 'O'). If they do, it returns 1, indicating a win.

2. The following `else if` conditions perform similar checks for other possible winning combinations, such as the horizontal middle and bottom rows, vertical columns, and diagonal lines.

```c
else if (square[4] == square[5] && square[5] == square[6])
    return 1;
```
```c
else if(square[7] == square[8] && square[8] == square[9])
    return 1;
```
```c
else if(square[1] == square[4] && square[4] == square[7])
    return 1;
```
```c
else if(square[2] == square[5] && square[5] == square[8])
    return 1;
```
```c
else if(square[3] == square[6] && square[6] == square[9])
    return 1;
```
```c
else if(square[1] == square[5] && square[5] == square[9])
    return 1;
```
```c
else if(square[3] == square[5] && square[5] == square[7])
    return 1;
```

3. If none of the winning conditions are met, the next condition checks if all the squares are filled with marks (neither 'X' nor 'O'):

```c
else if(square[1] != '1' && square[2] != '2' && square[3] != '3' && square[4] !='4' && square[5] != '5' && square[6] != '6' && square[7] != '7' && square[8] != '8' && square[9] != '9')
    return 0;
```

If this condition is true, it means all squares are filled, and there's no winner. It returns 0, indicating a draw.

4. Finally, if none of the above conditions are met, the function returns -1:

```c
else 
    return -1;
```

This indicates that the game is still ongoing.

In summary, this `checkWin()` function comprehensively examines the Tic Tac Toe board to determine whether a player has won (returns 1), the game is a draw (returns 0), or the game is still ongoing (returns -1).


void drawBoard(){

    system("cls");
    
    printf("\n\n\t Tic Tac Toe \n\n");
    
    printf("Player1 (X) - Player2 (O) \n\n\n");
    
    printf("     |     |     \n");
    
    printf("  %c  |  %c  |  %c  \n",square[1],square[2],square[3]);
    
    printf("_____|_____|_____\n");
    
    printf("     |     |     \n");
    
    printf("  %c  |  %c  |  %c  \n",square[4],square[5],square[6]);
    
    printf("_____|_____|_____\n");
    
    printf("     |     |     \n");
    
    printf("  %c  |  %c  |  %c  \n",square[7],square[8],square[9]);
    
    printf("     |     |     \n");    
    
}
```
`drawBoard()` is used to display the current state of the Tic Tac Toe board on the console. It uses the `square` array to represent the board, and it employs formatted `printf` statements to create the visual layout.

Here's a step-by-step explanation of the `drawBoard()` function:

1. `system("cls");` - This line clears the console screen using the "cls" command, providing a clean display for the updated board.

2. `printf("\n\n\t Tic Tac Toe \n\n");` - Prints the game title with some spacing for clarity.

3. `printf("Player1 (X) - Player2 (O) \n\n\n");` - Displays a legend indicating which mark corresponds to which player.

4. The next set of `printf` statements construct the visual representation of the Tic Tac Toe board, including the square contents.

5. For each row, the `printf` statements create a layout with a central line represented by '|', separating the board squares.

6. The `%c` format specifier is used to print the character values stored in the `square` array, displaying either 'X', 'O', or the square number.

7. The layout includes horizontal lines (`_____`) to demarcate rows.

8. The final layout provides a clear view of the game board.

In summary, `drawBoard()` is responsible for visually representing the current state of the Tic Tac Toe board on the console, allowing players to visualize their moves and the overall progress of the game.

In summary, this code creates a command-line Tic Tac Toe game where players take turns making moves. The game checks for win conditions and ends when a player wins or the game results in a draw. The current state of the game is displayed on the console.
