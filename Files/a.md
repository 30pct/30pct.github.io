### RSA Encryption Algorithm

#### Step 1: Key Generation

1. Select two distinct large prime numbers, $p$ and $q$:

   $p, q \in \mathbb{P}$

2. Compute the modulus $n$:

   $n = p \times q$

3. Calculate the totient $\phi(n)$:

   $\phi(n) = (p - 1)(q - 1)$

4. Choose the public exponent $e$:

   $1 < e < \phi(n)$ and $\gcd(e, \phi(n)) = 1$

5. Compute the private exponent $d$:

   $d \times e \equiv 1 \pmod{\phi(n)}$

6. The public key is $(e, n)$ and the private key is $(d, n)$.

#### Step 2: Encryption

1. Represent the plaintext message $m$:

   $m \in \{0, 1, \ldots, n-1\}$

2. Compute the ciphertext $c$:

   $c \equiv m^e \pmod{n}$

#### Step 3: Decryption

1. Recover the plaintext $m$ from the ciphertext $c$:

   $m \equiv c^d \pmod{n}$
