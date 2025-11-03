# Week 1: Introduction to Basic Ciphers and Cryptography

## What is Cryptography?

**Cryptography** is the science of hiding information so that only the right people can read it.  
You take a **message** (called _plaintext_), use some method or rule to **scramble** it, and you get a **coded message** (called _ciphertext_).  
The reverse process — turning ciphertext back into plaintext — is called **decryption**.

---

### 1️. Base64 Encoding

**Idea:**  
Base64 isn’t really a _cipher_ — it’s an _encoding_ method. It doesn’t hide data securely, it just converts it into a format that can be safely transmitted (like in emails or URLs).

**How it works:**

- Each character is converted into binary (ASCII value).
- The bits are grouped in sets of 6.
- Each 6-bit group is mapped to one of 64 possible characters:
  - 0–25 A–Z
  - 26–51 a–z
  - 52–61 0–9
  - 62 +
  - 63 /
- Base64 converts every 3 bytes (24 bits) of data into 4 Base64 characters.
  If data does not have bytes in multiple of 3 then padding is done with (=) to make the output length of 4.
  If there is 1 byte extra then two(==) comes.
  If there are 2 bytes extra then one = come.

**Example :** - HELLO

**Letter ASCII Binary**

- H - 72 - 01001000
- E - 69 - 01000101
- L - 76 - 01001100
- L - 76 - 01001100
- O - 79 - 01001111

After combining all bits and dividing them in 6 bits:

- 010010 - S
- 000100 - E
- 010101 - V
- 001100 - M
- 010011 - T
- 000100 - E
- 1111 - 111100 - 8

**And now due to only 5 bytes data hence 2 remainder we have to add a = at the end.**

### Therefore HELLO - SEVMTE8=

**Note:** Base64 is **not encryption** — anyone can decode it easily.

---

### 2. Caesar Cipher

**Idea:**  
One of the oldest and simplest ciphers, used by _Julius Caesar_.  
It works by shifting every letter in the message by a fixed number(key) of positions in the alphabet.

**Example :**
**Message:** `HELLO`  
**Key:** 3

We shift each letter **3 places forward** in the alphabet.

- H --> K
- E --> H
- L --> O
- L --> O
- O --> R

**Encrypted message = `KHOOR`**

To get the original text back, just **shift backward by 3**.

`KHOOR → HELLO`

**Key Points**

- Works only on alphabets.
- Same key is used for both encryption and decryption.
- Very easy to break (try all 26 shifts).
- Great for learning — not for real security.

---

# 3. Vigenère Cipher

**Idea**
The **Vigenère Cipher** is like a smarter version of the Caesar Cipher.  
Instead of using a single number as the key, it uses a **word** —  
and each letter of that key decides how much to shift each letter in the message.

So, every letter is encrypted with a **different shift**, based on the key.

## How It Works

- A key letter **A** means shift by **0**.
- A key letter **B** means shift by **1**.
- A key letter **C** means shift by **2**, and so on.

So, if your message is longer than the key, you **repeat the key** until both are the same length.

Each letter of the message is then encrypted with its corresponding letter of the key:

## Step-by-Step Example

**Plaintext:** `HELLO`

**Key:** `KEY`

### Step 1: Repeat the key

We repeat the key to match the message length:

First, repeat the key to match the message length:

**Key:** `KEYKE`

### Step 2: Convert Letters to numbers

- H --> 7 -- K --> 10
- E --> 4 -- E --> 4
- L --> 11 -- Y --> 24
- L --> 11 -- K --> 10
- O --> 14 -- E --> 4

### Step 3: Encrypt each letter with its key

- H --> 17 -- R
- E --> 8 -- I
- L --> 35 -- J
- L --> 21 -- V
- O --> 18 -- S

**Encrypted Text = `RIJVS`**

To decrypt, subtract the key value instead of adding
