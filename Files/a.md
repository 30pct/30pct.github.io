Sure! RSA (Rivest-Shamir-Adleman) is a widely used public-key cryptosystem that allows secure data transmission. It is based on the mathematical difficulty of factoring large prime numbers. Below is a step-by-step explanation of how RSA works:

### 1. Key Generation

#### Step 1: Choose two large prime numbers
Choose two distinct large prime numbers \( p \) and \( q \).

\[
p = \text{large prime number}
\]
\[
q = \text{large prime number}
\]

#### Step 2: Compute \( n \)
Compute \( n \) as the product of \( p \) and \( q \). The value \( n \) will be used as the modulus for both the public and private keys.

\[
n = p \times q
\]

#### Step 3: Compute Euler's Totient Function \( \phi(n) \)
Compute Euler's Totient Function \( \phi(n) \), which is given by:

\[
\phi(n) = (p - 1) \times (q - 1)
\]

#### Step 4: Choose the public exponent \( e \)
Choose an integer \( e \) such that \( 1 < e < \phi(n) \) and \( \gcd(e, \phi(n)) = 1 \). The integer \( e \) is the public exponent.

\[
\gcd(e, \phi(n)) = 1
\]

#### Step 5: Compute the private exponent \( d \)
Compute the private exponent \( d \) as the modular multiplicative inverse of \( e \) modulo \( \phi(n) \). This means:

\[
d \times e \equiv 1 \ (\text{mod} \ \phi(n))
\]

In other words, \( d \) is the integer such that:

\[
d = e^{-1} \ (\text{mod} \ \phi(n))
\]

### 2. Public and Private Keys

- **Public Key**: The public key is the pair \( (e, n) \).
- **Private Key**: The private key is the pair \( (d, n) \).

### 3. Encryption

To encrypt a message \( M \) (where \( M \) is an integer such that \( 0 \leq M < n \)), the sender computes the ciphertext \( C \) using the recipient's public key \( (e, n) \):

\[
C = M^e \ (\text{mod} \ n)
\]

### 4. Decryption

To decrypt the ciphertext \( C \), the recipient uses their private key \( (d, n) \) to compute the original message \( M \):

\[
M = C^d \ (\text{mod} \ n)
\]

### 5. Example

Let's go through a simple example with small numbers:

1. **Choose primes**: \( p = 61 \), \( q = 53 \)
2. **Compute \( n \)**: \( n = 61 \times 53 = 3233 \)
3. **Compute \( \phi(n) \)**: \( \phi(n) = (61 - 1) \times (53 - 1) = 60 \times 52 = 3120 \)
4. **Choose \( e \)**: Let \( e = 17 \) (which is a common choice and satisfies \( \gcd(17, 3120) = 1 \))
5. **Compute \( d \)**: Find \( d \) such that \( d \times 17 \equiv 1 \ (\text{mod} \ 3120) \). The value of \( d \) is \( 2753 \).

- **Public Key**: \( (e, n) = (17, 3233) \)
- **Private Key**: \( (d, n) = (2753, 3233) \)

**Encryption**: Suppose the message \( M = 65 \).

\[
C = 65^{17} \ (\text{mod} \ 3233) = 2790
\]

**Decryption**: To recover \( M \) from \( C \):

\[
M = 2790^{2753} \ (\text{mod} \ 3233) = 65
\]

Thus, the original message \( M = 65 \) is successfully recovered.

### 6. Security

The security of RSA relies on the difficulty of factoring the large number \( n \) into its prime factors \( p \) and \( q \). If an attacker can factor \( n \), they can compute \( \phi(n) \) and subsequently determine the private key \( d \). However, for sufficiently large \( p \) and \( q \), factoring \( n \) is computationally infeasible.

This concludes the step-by-step explanation of the RSA algorithm!
