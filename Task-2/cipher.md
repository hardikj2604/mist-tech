# Task-2 : Some Advanced Ciphers

### In Week 1, you learned ciphers that use simple shifting and substitution (Caesar, Vigenère).

### Now we move to slightly more advanced classical ciphers that involve patterns, mathematics, and matrices.

## Some ciphers we will learn now are:

- Hill Cipher
- Rail Fence Cipher
- Affine

---

### 1️. Hill Cipher :

**Idea:**  
The Hill Cipher encrypts **multiple letters at the same time** using a **matrix** (a grid of numbers).  
It converts letters → numbers → multiplies them by a **key matrix** → converts back to letters.

**How it works:**

1. Convert letters to numbers (A=0, B=1, ..., Z=25)
2. Group message letters according to matrix size (usually pairs)
3. Multiply the number group by the key matrix
4. Take each result **mod 26**
5. Convert the numbers back to lettersomes.

Because it encrypts letters **together**, letter patterns are mixed and harder to analyze.

### Note: The key matrix must be **invertible modulo 26** (its determinant must be coprime with 26), or decryption won’t be possible.

### What is a “Group”?

**Group (block) size = matrix size**.

| Key Matrix Size | Group Size | Meaning                    |
| --------------- | ---------- | -------------------------- |
| 2×2             | 2 letters  | Encrypt letters in pairs   |
| 3×3             | 3 letters  | Encrypt letters in triples |

If the last block is short, **pad** it (commonly with `X`).

Example of grouping with a 2×2 key:
HELLO -> HE LL OX

### Example: Encrypt “HELLO” with a 2×2 key

**Key Matrix (K):**

[3 3]

[2 5]

**1) Group the plaintext (block size = 2):**

HELLO → HE LL OX

**2) Convert letters to numbers:**
H=7, E=4, L=11, L=11, O=14, X=23

**3) Encrypt each group:**

- HE

  [3 3] [7] = [3(7) + 3(4)] = [33]

  [2 5] [4] = [2(7) + 5(4)] = [34]

  [ 33 mod 26 ] = [ 7 ]

  [ 34 mod 26 ] = [ 8 ]

  7 -> H | 8 -> I

  HE -> HI

- LL

  [3 3] [11] = [3(11) + 3(11)] = [66]

  [2 5] [11] = [2(11) + 5(11)] = [77]

  [ 66 mod 26 ] = [ 14 ]

  [ 77 mod 26 ] = [ 25 ]

  14 -> O | 25 -> Z

  LL -> OZ

- OX

  [3 3] [14] = [3(14) + 3(23)] = [111]

  [2 5] [23] = [2(14) + 5(23)] = [143]

  [ 111 mod 26 ] = [ 7 ]

  [ 143 mod 26 ] = [ 13 ]

  7 -> H | 13 -> N

  OX -> HN

#### HELLO → HIOZHN

---

### 2. Rail Fence Cipher

**Idea:**  
A **transposition** cipher: it **rearranges** letters without changing them.  
Write the message in a **zigzag** across a chosen number of rails (rows), then read row by row.

### How It Works (3 rails example)

1. Choose rails (e.g., 3).
2. Write letters down and up in a zigzag across rails.
3. Read each rail row-by-row to form the ciphertext.

**Example :**
**Message:** `HELLO WORLD`  
**Rail:** 3

**Step 1 — Remove spaces**

HELLOWORLD

**Step 2 — Assign letters in zigzag**
Rail pattern for 3 rails is: **0 → 1 → 2 → 1 → 0 → 1 → 2 → 1 → 0 → 1**

Rail 0: H O L
Rail 1: E L W R D
Rail 2: L O

**Step 3 - Combine:**
HOLELWRDLO

#### HELLO WORLD - HOLELWRDLO

---

### 3. Affine Cipher

**Idea**
The Affine Cipher is a **mathematical substitution cipher**.  
Each letter (A=0, B=1, … Z=25) is transformed using the formula:
**E(x) = (a·x + b) mod 26**

- `a` and `b` are keys.
- `a` must satisfy:  
  `gcd(a, 26) = 1`  
  so that the cipher can be decrypted (i.e., `a` has an inverse mod 26).

This cipher changes each letter in a more complex way than the Caesar Cipher.

### How It Works

1. Convert letters to numbers (A=0, B=1, … Z=25).
2. Apply the encryption formula `E(x) = (a·x + b) mod 26`.
3. Convert numbers back to letters to get the ciphertext.

### Example (a = 5, b = 8)

Encrypt the message: HELLO

Convert letters:

H = 7
E = 4
L = 11
L = 11
O = 14

Apply the formula to each letter:

| Letter | x   | (5·x + 8) mod 26                   | Result |
| ------ | --- | ---------------------------------- | ------ |
| H      | 7   | (5·7 + 8) mod 26 = 43 mod 26 = 17  | R      |
| E      | 4   | (5·4 + 8) mod 26 = 28 mod 26 = 2   | C      |
| L      | 11  | (5·11 + 8) mod 26 = 63 mod 26 = 11 | L      |
| L      | 11  | (5·11 + 8) mod 26 = 63 mod 26 = 11 | L      |
| O      | 14  | (5·14 + 8) mod 26 = 78 mod 26 = 0  | A      |

### ✅ Final Ciphertext

HELLO → RCLLA
