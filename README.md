## EX : 5 IMPLEMENTATION OF RAIL FENCE CIPHER

## AIM:

To develop a simple C program to implement Rail Fence Cipher.


## ALGORITHM:
#### 1.	To perform the Encryption Process
#### •	Input the plaintext string from the user.
#### •	Calculate the length of the plaintext.
#### •	Create the ciphertext using two rails:
#### a.	First, collect characters at even indices (i.e., 0, 2, 4, …).
#### b.	Then, collect characters at odd indices (i.e., 1, 3, 5, …).
#### c.	Combine both parts to form the ciphertext.
#### •	Display the encrypted ciphertext.

#### 2.	To perform the Decryption Process:
#### •	Calculate the length of the ciphertext.
#### •	Find the midpoint:
#### ◦	a. If the length is even, midpoint = length / 2.
#### ◦	b. If the length is odd, midpoint = (length / 2) + 1.
#### •	Reconstruct the original message:
#### a.	Take the first half as characters from even positions.
#### b.	Take the second half as characters from odd positions.
#### c.	Merge both using alternating positions.

#### 3.	Display the decrypted plaintext.



## PROGRAM:

    #include <stdio.h>
    #include <string.h>
    
    int main() {
        int i, j, k, l;
        char a[20], c[20], d[20];
    
        printf("\n\t\tRAIL FENCE TECHNIQUE\n");
    
        // Safely getting input string using fgets
        printf("\nEnter the input string: ");
        fgets(a, sizeof(a), stdin);
    
        // Removing the newline character if it exists
        a[strcspn(a, "\n")] = '\0';
    
        l = strlen(a); // Get the length of the input string
    
        // Rail fence encryption: first collect even indices, then odd
        for (i = 0, j = 0; i < l; i++) {
            if (i % 2 == 0) {
                c[j++] = a[i];
            }
        }
        for (i = 0; i < l; i++) {
            if (i % 2 == 1) {
                c[j++] = a[i];
            }
        }
        c[j] = '\0'; // Null-terminate the encrypted string
    
        printf("\nCipher text after applying rail fence: %s\n", c);
    
        // Rail fence decryption
        if (l % 2 == 0) {
            k = l / 2;
        } else {
            k = (l / 2) + 1;
        }
    
        // Reconstructing the original text
        for (i = 0, j = 0; i < k; i++) {
            d[j] = c[i];
            j += 2;
        }
        for (i = k, j = 1; i < l; i++) {
            d[j] = c[i];
            j += 2;
        }
        d[l] = '\0'; // Null-terminate the decrypted string
    
        printf("\nText after decryption: %s\n", d);
    
        return 0; // Properly return from main
    }

## OUTPUT:

<img width="1643" height="867" alt="image" src="https://github.com/user-attachments/assets/63bf60ad-d805-42c4-b093-9d22c845e0ab" />

## RESULT:
The program implementing the Rail Fence cipher for encryption and decryption has been successfully	executed,	and	the	results	have	been	verified.
