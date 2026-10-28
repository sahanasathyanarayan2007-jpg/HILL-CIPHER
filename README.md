# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char text[100];
    int key[2][2] = {{3, 3}, {2, 5}};
    int a, b, c, d, i;

    printf("Enter plaintext: ");
    scanf("%99s", text);

    for (i = 0; text[i] != '\0'; i++)
        text[i] = toupper(text[i]);

    int len = strlen(text);

    if (len % 2 != 0) {
        text[len] = 'X';
        text[len + 1] = '\0';
        len++;
    }

    printf("Encrypted text: ");

    for (i = 0; i < len; i += 2) {
        a = text[i] - 'A';
        b = text[i + 1] - 'A';

        c = (key[0][0] * a + key[0][1] * b) % 26;
        d = (key[1][0] * a + key[1][1] * b) % 26;

        printf("%c%c", c + 'A', d + 'A');
    }

    printf("\n");
    return 0;
}
```

## OUTPUT
<img width="1600" height="749" alt="WhatsApp Image 2026-10-28 at 9 17 46 AM" src="https://github.com/user-attachments/assets/2856142a-435d-4475-a5bb-be970f4226df" />


## RESULT
implement the hill cipher substitution techniques was done.
