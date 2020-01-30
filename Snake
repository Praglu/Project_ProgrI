// snake.cpp : This file contains the 'main' function. Program execution begins and ends there.
//
#include <iostream>
#include <windows.h>
#include <deque>
#include <conio.h>
#include <time.h>


#define WIDTH 70
#define HEIGHT 25

using namespace std;

HANDLE h = GetStdHandle(STD_OUTPUT_HANDLE);
COORD c;

deque <char> x, y;

enum dir { UP, RIGHT, DOWN, LEFT } dir;

void GameOver()
{
	system("Pause > nul");
	system("cls");
	cout << "GameOver" << endl;
	system("Pause > nul");
	exit(0);
}
void gotoxy(char x, char y)
{
	c.X = x;
	c.Y = y;
	SetConsoleCursorPosition(h, c);
}

int main()
{
	srand(time(NULL));
	cout << "Kliknij aby rozpoczac" << endl;
	_getch();
	system("cls");
	for (int i = 0; i < WIDTH; i++)
		cout << static_cast<char>(219);

	cout << endl;

	for (int i = 0; i < HEIGHT; i++)
	{
		cout << endl << static_cast<char>(219);
		gotoxy(WIDTH - 1, i);
		cout << static_cast<char>(219);
	}

	cout << endl;

	for (int i = 0; i < WIDTH; i++)
		cout << static_cast<char>(219);

	x.push_front(WIDTH / 2);
	y.push_front(HEIGHT / 2);

	gotoxy(x.front(), y.front());
	cout << static_cast<char>(219);


	for (;;)
	{
		if (_kbhit())
		{
			switch (_getch())
			{
			case 'W':
			case 'w':
				if (dir != DOWN)
					dir = UP;
				break;
			case 'D':
			case 'd':
				if (dir != LEFT)
					dir = RIGHT;
				break;
			case 'S':
			case 's':
				if (dir != UP)
					dir = DOWN;
				break;
			case 'A':
			case 'a':
				if (dir != RIGHT)
					dir = LEFT;
				break;
			}
		}

		x.push_front(x.front());
		y.push_front(y.front());

		switch (dir)
		{
		case UP:
			y.front()--;
			break;
		case RIGHT:
			x.front()++;
			break;
		case DOWN:
			y.front()++;
			break;
		case LEFT:
			x.front()--;
			break;
		}

		for (int i = 1; i < x.size(); i++)
		{
			if (x.front() == x[i] && y.front() == y[i])
				GameOver();
		}

		if (x.front() == 0 || x.front() == WIDTH || y.front() == 0 || y.front() == HEIGHT)
			GameOver();

		SetConsoleTextAttribute(h, 14);

		gotoxy(x.front(), y.front());
		cout << static_cast<char>(219);

		gotoxy(x.back(), y.back());
		cout << static_cast<char>(32);

		if (rand() % 8)
		{
			x.pop_back();
			y.pop_back();
		}

		Sleep(100);
	}

	cout << endl;
	system("PAUSE");
}
