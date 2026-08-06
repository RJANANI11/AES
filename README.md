# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:
```
#include <stdio.h>
#include <string.h>

void simpleAESEncrypt(char *plaintext, char *key, char *ciphertext)
{
    int i;

    for (i = 0; i < strlen(plaintext); i++)
    {
        ciphertext[i] = plaintext[i] ^ key[i % strlen(key)];
    }

    ciphertext[i] = '\0';
}

void simpleAESDecrypt(char *ciphertext, char *key, char *decryptedText)
{
    int i;

    for (i = 0; i < strlen(ciphertext); i++)
    {
        decryptedText[i] = ciphertext[i] ^ key[i % strlen(key)];
    }

    decryptedText[i] = '\0';
}

void printASCII(char *ciphertext)
{
    int i;

    printf("Encrypted Message (ASCII values): ");

    for (i = 0; i < strlen(ciphertext); i++)
    {
        printf("%d ", (unsigned char)ciphertext[i]);
    }

    printf("\n");
}

int main()
{
    char plaintext[100];
    char key[100];
    char ciphertext[100];
    char decryptedText[100];

    printf("Enter the plaintext: ");
    scanf("%99s", plaintext);

    printf("Enter the key: ");
    scanf("%99s", key);

    simpleAESEncrypt(plaintext, key, ciphertext);

    printASCII(ciphertext);

    simpleAESDecrypt(ciphertext, key, decryptedText);

    printf("Decrypted Message: %s\n", decryptedText);

    return 0;
}
```

# OUTPUT:
<img width="1446" height="1013" alt="image" src="https://github.com/user-attachments/assets/0420ae4c-57ec-4c0b-b3f1-3561223f6177" />


# RESULT:
Thus the program Advanced encryption standard algorithm is successfully executed.
