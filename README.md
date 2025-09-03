## Exp:1 IMPLEMENTATION OF CAESER CIPHER 

## AIM: 
To encrypt and decrypt the given message by using Caeser Cipher encryption algorithm. 
  
 ## ALGORITHM: 
1. Calculate the length of the plaintext. 
2. For each character in the plaintext:  
 a. Add the key to the character to get the cipher character.  
 b. If the result exceeds 'Z' for uppercase or 'z' for lowercase, subtract 26 to wrap within the  alphabet.  
3. Display the encrypted text.  
4. For decryption, subtract the key from each character of the ciphertext.  
 a. If the result is less than 'A' for uppercase or 'a' for lowercase, add 26 to wrap within the  alphabet.  
5. Display the decrypted text.  

## PROGRAM: 
~~~
#include<stdio.h> 
#include<string.h> 
#include<ctype.h>  
int main()  
{ 
char plain[100], cipher[100]; int key, i, length; 
printf("Enter the plain text: "); 
scanf("%s", plain);  
printf("Enter the key value: "); 
scanf("%d", &key);  
printf("\nPLAIN TEXT: %s", plain); 
printf("\nENCRYPTED TEXT: "); 
length = strlen(plain); 
for (i = 0; i < length; i++) 
{ 
cipher[i] = plain[i] + key; 
// Handling uppercase letters 
if (isupper(plain[i]) && cipher[i] > 'Z') 
{ 
cipher[i]= cipher[i] - 26; 
} 
// Handling lowercase letters 
if (islower(plain[i]) && cipher[i] > 'z') 
{ 
cipher[i] = cipher[i] - 26; 
} 
printf("%c", cipher[i]); 
} 
cipher[length] = '\0'; // Null-terminate the cipher text string 
printf("\nDECRYPTED TEXT: "); 
for (i = 0; i < length; i++) 
{  
plain[i] = cipher[i] - key; 
// Handling uppercase letters 
if (isupper(cipher[i]) && plain[i] < 'A') 
{ 
plain[i] = plain[i] + 26; 
} 
// Handling lowercase letters 
if (islower(cipher[i]) && plain[i] < 'a') 
{ 
plain[i] = plain[i] + 26; 
} 
printf("%c", plain[i]); 
} 
plain[length] = '\0'; // Null-terminate the plain text string return 0; 
}
~~~

## OUTPUT: 
<img width="416" height="181" alt="Screenshot 2025-08-28 133916" src="https://github.com/user-attachments/assets/3d522011-883f-4e02-813b-bce57e513a36" />


## RESULT: 
The program implementing the Caesar cipher for encryption and decryption has been successfully  executed, and the results have been verified.
