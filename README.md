# Vigenere Cipher
Vigenere Cipher using with different key values

# AIM:

To develop a simple C program to implement Vigenere Cipher.

## DESIGN STEPS:

### Step 1:

Design of Vigenere Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 
ALGORITHM DESCRIPTION:
The Vigenere cipher is a method of encrypting alphabetic text by using a series of different Caesar ciphers based on the letters of a keyword. It is a simple form of polyalphabetic substitution.To encrypt, a table of alphabets can be used, termed a Vigenere square, or Vigenere table. It consists of the alphabet written out 26 times in different rows, each alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses a different alphabet from one of the rows used. The alphabet at each point depends on a repeating keyword.



## PROGRAM:
```
#include <stdio.h>
#include <string.h>

void vigenereEncrypt(char* text, const char* key) {
    int textLen = strlen(text);
    int keyLen = strlen(key);

    for (int i = 0, j = 0; i < textLen; i++) {
        char c = text[i];
        if (c >= 'A' && c <= 'Z') {
            text[i] = ((c - 'A' + key[j % keyLen] - 'A') % 26) + 'A';
            j++;
        } else if (c >= 'a' && c <= 'z') {
            text[i] = ((c - 'a' + key[j % keyLen] - 'A') % 26) + 'a';
            j++;
        }
    }
}

void vigenereDecrypt(char* text, const char* key) {
    int textLen = strlen(text);
    int keyLen = strlen(key);

    for (int i = 0, j = 0; i < textLen; i++) {
        char c = text[i];
        if (c >= 'A' && c <= 'Z') {
            text[i] = ((c - 'A' - (key[j % keyLen] - 'A') + 26) % 26) + 'A';
            j++;
        } else if (c >= 'a' && c <= 'z') {
            text[i] = ((c - 'a' - (key[j % keyLen] - 'A') + 26) % 26) + 'a';
            j++;
        }
    }
}

int main() {
    const char* key = "KEY";
    char message[] = "Abdur Rahman Basil A H";

    vigenereEncrypt(message, key);
    printf("Encrypted Message: %s\n", message);

    vigenereDecrypt(message, key);
    printf("Decrypted Message: %s\n", message);

    return 0;
}

```
## OUTPUT:
![image](https://github.com/user-attachments/assets/676cc78c-e090-462c-b2e0-f47a4c1f8594)

## RESULT:
The program is executed successfully
