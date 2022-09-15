// Peter Wipf ITT-310
//Date 9/15/2022
//Create a Tic Tac Toe Game

#include "stdio.h""

/*
int board[25] = 
{
	:,:,:,:,:,
	:,:,O,:,:,
	:,X,X,:,:,
	:,:,:,O,:,
	:,:,:,:,:,
}

*/

    /// Create the constants. XS and OS for player pieces

const XS = 1;
const OS = 2;
const BORDER = 8;
const EMPTY = 0;
const int ConvertTo25[9] = 
{
	6,7,8,
	11,12,13,
	16,17,18

};

// Tic Tac Toe board

void InitialiseBoard(int* board) 
{
	int index = 0;

	for (index = 0; index < 25; ++index)
	{
		board[index] = BORDER;
	}

	for (index = 0; index < 9; ++index) 
	{
		board[ConvertTo25[index]] = EMPTY;
	}
}

// Welcome and Let's Play screen. 

void PrintBoard(const int* board) 
{
	int index = 0;
	printf("Welcome! Let's Play\n");
	for (index = 0; index < 25; ++index) 
	{
		if (index !=0 && index%5 ==0)
		{
			printf("\n");
		}
		printf("%4d", board[index]);
	}
}

// Add more player moves. (Next Player)  board[ConvertTo25[7]] = OS/XS

int main() {

	int board[25];
    InitialiseBoard(&board[0]);
	board[ConvertTo25[7]] = OS;
	board[ConvertTo25[3]] = XS;
	board[ConvertTo25[0]] = OS;
	board[ConvertTo25[8]] = XS;
	PrintBoard(&board[0]);
}
