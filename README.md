## NAME : THIRUMALAI K
## REG NO : 212224240176
## DATE : 02/02/26

# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM

```C
#include <stdio.h>
#include <string.h>

int main()
{
    char msg[100];
    int rails, i, j, row = 0, dir = 1;

    printf("Enter the input: ");
    scanf("%s", msg);

    printf("Enter key value: ");
    scanf("%d", &rails);

    int len = strlen(msg);
    char rail[10][100];

    for(i=0;i<rails;i++)
        for(j=0;j<len;j++)
            rail[i][j] = '*';

    for(i=0;i<len;i++)
    {
        rail[row][i] = msg[i];
        row += dir;

        if(row == rails-1 || row == 0)
            dir = -dir;
    }

    printf("Encrypted text: ");
    for(i=0;i<rails;i++)
        for(j=0;j<len;j++)
            if(rail[i][j] != '*')
                printf("%c", rail[i][j]);

    return 0;
}
```

# OUTPUT
<img width="451" height="150" alt="image" src="https://github.com/user-attachments/assets/1bff13f6-a22a-4c2f-8fec-98fe06da4137" />


# RESULT
Thus the implementation of Rail-Fence-Program had been executed successully.
