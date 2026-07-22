# EX. NO: 3 - HILL CIPHER

### Name: Kiruthiga.B

### Reg.no: 212224040160


# AIM:

To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. 

STEP-2: Split the plain text into groups of length three.

STEP-3: Arrange the keyword in a 3*3 matrix.

STEP-4: Multiply the two matrices to obtain the cipher text of length three.

STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 

```
#include <stdio.h>
#include <string.h>

int main()
{
    int key[3][3] = {
        {6, 24, 1},
        {13, 16, 10},
        {20, 17, 15}
    };

    int inverseKey[3][3] = {
        {8, 5, 10},
        {21, 8, 21},
        {21, 12, 8}
    };

    char plaintext[20];
    int plain[3], cipher[3], decrypt[3];
    int i, j, sum;

    printf("Enter 3-letter Plain Text (Uppercase): ");
    scanf("%s", plaintext);
    printf("\nPlain Text Values: ");
    for(i = 0; i < 3; i++)
    {
        plain[i] = plaintext[i] - 'A';
        printf("%d ", plain[i]);
    }

    for(i = 0; i < 3; i++)
    {
        sum = 0;
        for(j = 0; j < 3; j++)
        {
            sum += key[i][j] * plain[j];
        }
        cipher[i] = sum % 26;
    }

    
    printf("\nEncrypted Text: ");
    for(i = 0; i < 3; i++)
    {
        printf("%c", cipher[i] + 'A');
    }

  
    for(i = 0; i < 3; i++)
    {
        sum = 0;
        for(j = 0; j < 3; j++)
        {
            sum += inverseKey[i][j] * cipher[j];
        }
        decrypt[i] = sum % 26;
    }

    // Display Decrypted Text
    printf("\nDecrypted Text: ");
    for(i = 0; i < 3; i++)
    {
        printf("%c", decrypt[i] + 'A');
    }

    return 0;
}
```

## OUTPUT

<img width="587" height="255" alt="image" src="https://github.com/user-attachments/assets/085d893f-40d9-42fd-b123-25d3ee7536ac" />


## RESULT

Thus,Hill cipher has been successfully implemented.
