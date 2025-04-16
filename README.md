## Implementation-of-DES-Encryption-and-Decryption

EX-NO-7-Implement-DES-Encryption-and-Decryption
## Aim:
To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:
DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
DES uses a Feistel network structure with 16 rounds of processing for encryption.
DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.
## Program:
```
Name:MOHAMED AZEEM N
Reg No:212222110026

#include <stdio.h>
#include <string.h>

// Function to perform a simple XOR-based encryption (AES-like)
void encrypt(char *message, char *key, char *encryptedMessage, int messageLength) {
    int keyLength = strlen(key);

    for (int i = 0; i < messageLength; i++) {
        // Encrypt by XORing message byte with key byte (simplified)
        encryptedMessage[i] = message[i] ^ key[i % keyLength];
    }
    encryptedMessage[messageLength] = '\0';  // Null-terminate the encrypted message
}

// Function to perform decryption (XOR again with the same key)
void decrypt(char *encryptedMessage, char *key, char *decryptedMessage, int messageLength) {
    int keyLength = strlen(key);

    for (int i = 0; i < messageLength; i++) {
        // Decrypt by XORing encrypted byte with key byte (simplified)
        decryptedMessage[i] = encryptedMessage[i] ^ key[i % keyLength];
    }
    decryptedMessage[messageLength] = '\0';  // Null-terminate the decrypted message
}

int main() {
    char message[100];
    char key[100];
    printf("\n                *****Simualtion of AES Encryption and Decryption*****\n\n");
    
    // Get user input for the message
    printf("Enter the message to encrypt: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = '\0';  // Remove newline character if present

    // Get user input for the key
    printf("Enter the encryption key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = '\0';  // Remove newline character if present

    int messageLength = strlen(message);
    
    // Buffers to hold encrypted and decrypted messages
    char encryptedMessage[100];
    char decryptedMessage[100];
    
    // Encrypt the message
    encrypt(message, key, encryptedMessage, messageLength);
    printf("Original Message: %s\n", message);
    printf("Encrypted Message: ");
    
    // Print encrypted message in hex format
    for (int i = 0; i < messageLength; i++) {
        printf("%02X ", (unsigned char)encryptedMessage[i]);
    }
    printf("\n");
    
    // Decrypt the message
    decrypt(encryptedMessage, key, decryptedMessage, messageLength);
    printf("Decrypted Message: %s\n", decryptedMessage);
    
    return 0;
}
```
## Output:
![image](https://github.com/user-attachments/assets/15cf6bef-95ca-41fc-9f84-3a8e265de7c7)

## Result:
The program is executed successfully


