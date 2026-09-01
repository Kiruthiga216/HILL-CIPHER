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
#include <ctype.h> 
int main() 
{ 
    char plain[10],cipher[10]; 
    int key,i,length; 
    int result; 
    printf(" Enter the plain text:"); 
    scanf("%s", plain); 
    printf(" Enter the key value:"); 
    scanf("%d", &key); 
    printf(" Plain Text: %s", plain); 
    printf("\n Encypted Text:"); 
    for(i=0, length = strlen(plain); i<length; i++) 
    { 
        cipher[i]=plain[i] + key; 
        if (isupper(plain[i]) && (cipher[i] > 'Z')) 
        cipher[i] = cipher[i] - 26; 
        if (islower(plain[i]) && (cipher[i] > 'z')) 
        cipher[i] = cipher[i] - 26; 
        printf("%c", cipher[i]); 
    } 
    printf("\n After Deryption: "); 
    for(i=0;i<length;i++) 
    { 
        plain[i]=cipher[i]-key; 
        if(isupper(cipher[i])&&(plain[i]<'A')) 
        plain[i]=plain[i]+26; 
        if(islower(cipher[i])&&(plain[i]<'a')) 
        plain[i]=plain[i]+26; 
        printf("%c",plain[i]); 
    } 
}
```

## OUTPUT


<img width="548" height="297" alt="image" src="https://github.com/user-attachments/assets/eb947771-938d-4b9d-a914-7a1168807643" />




## RESULT

Thus,Hill cipher has been successfully implemented.
