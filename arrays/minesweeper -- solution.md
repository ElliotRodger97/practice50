# Minesweeper

## Possible Solution
```c
#include <cs50.h>
#include <stdio.h>
#include <time.h>

#define HEIGHT 10
#define WIDTH 8
#define MINE_NUM 5

int main(void)
{
    // initialize field to be empty, and fill with 5 mines randomly located
    int field[HEIGHT][WIDTH] = {{0}};
    time_t t;
    srand((unsigned) time(&t));
    for (int k = 0; k < MINE_NUM; k++)
    {
        int i = rand() % HEIGHT;
        int j = rand() % WIDTH;
        // if mine has been planted in this location already, try again
        if (field[i][j] == 1)
            k--;
        else
            field[i][j] = 1;
    }
    
    // print out the location of the mines
    for (int i = 0; i < HEIGHT; i++)
            for (int j = 0; j < WIDTH; j++)
                {
                    if (field[i][j] == 1)
                        printf("mines are at %d, %d\n", i, j);
                }


}
```