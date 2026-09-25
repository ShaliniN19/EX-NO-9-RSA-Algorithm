# EX-NO-9-RSA-Algorithm
## NAME: SHALINI N
## REG NO: 212224040305

## AIM:
To Implement RSA Encryption Algorithm in Cryptography

## Algorithm:


Step 1: Design of RSA Algorithm  
The RSA algorithm is based on the mathematical difficulty of factoring the product of two large prime numbers. It involves generating a public and private key pair, where the public key is used for encryption, and the private key is used for decryption.

Step 2: Implementation in Python or C 
This algorithm can be implemented in languages like Python or C by performing large integer calculations for key generation, encryption, and decryption, utilizing libraries for modular arithmetic if necessary.

Step 3: Algorithm Description  
1. Key Generation:
   - Select two large prime numbers \( p \) and \( q \).
   - Calculate \( n = p \times q \), which will be used as the modulus.
   - Compute the totient \( \phi(n) = (p - 1)(q - 1) \).
   - Choose a public exponent \( e \) such that \( e \) is coprime with \( \phi(n) \).
   - Compute the private key \( d \), which is the modular inverse of \( e \) mod \( \phi(n) \).

2. Encryption:
   - Convert the plaintext message \( M \) into a numerical form \( m \) (such that \( 0 \le m < n \)).
   - Compute the ciphertext \( c \) using the formula: \( c = m^e \mod n \).

3. Decryption:
   - Use the private key \( d \) to recover \( m \) from \( c \) using: \( m = c^d \mod n \).
   - Convert \( m \) back into the original message \( M \).

Step 4: Mathematical Representation  
- Encryption: \( E(m) = m^e \mod n \)
- Decryption: \( D(c) = c^d \mod n \)

Step 5: **Security Foundation  
The security of RSA relies on the difficulty of factoring large numbers; thus, choosing sufficiently large prime numbers for \( p \) and \( q \) is crucial for security.

## Program:

```
#include <stdio.h>
#include <string.h>

long long power(long long b,long long e,long long n)
{
    long long r=1;
    while(e>0){
        if(e%2) r=r*b%n;
        b=b*b%n;
        e/=2;
    }
    return r;
}

int main()
{
    int n=3233,e=17,d=2753,i;
    char msg[50];

    printf("Enter message: ");
    fgets(msg,50,stdin);

    printf("Encrypted: ");
    for(i=0; msg[i]!='\0' && msg[i]!='\n'; i++)
        printf("%lld ",power(msg[i],e,n));

    printf("\nDecrypted: ");
    for(i=0; msg[i]!='\0' && msg[i]!='\n'; i++)
        printf("%c",(char)power(power(msg[i],e,n),d,n));

    return 0;
}
```


## Output:


<img width="1345" height="735" alt="image" src="https://github.com/user-attachments/assets/eef56cb2-4228-4329-bbc4-818cf8ca9980" />



## Result:
 The program is executed successfully.
