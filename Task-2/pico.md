# Rail Fence CTF

A type of transposition cipher is the rail fence cipher, which is described online. Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it?
This is the message :
**Ta \_7N6D49hlg:W3D_H3C31N**A97ef sHR053F38N43D7B i33\_\_\_N6\*\*

Put the decoded message in the picoCTF flag format, picoCTF{decoded_message}.

### Solve

**Flag:** `picoctf{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_4A76B997}`

The name _"rail-fence"_ itself suggested that a **Rail Fence Cipher** was being used.  
A Rail Fence Cipher rearranges the characters in a zigzag pattern across multiple rows (rails).

The challenge explicitly mentioned **4 rails**, which made the attack straightforward.  
I downloaded the encrypted message from the prompt and then applied a **Rail Fence (4 rails) decryption**.

I used an online Rail Fence tool to test the ciphertext with _exactly 4 rails_:

Once the correct rail count was applied, the output was clearly readable: WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_4A76B997

Below is the decoding process:

![Rail Fence Decoder](./Screenshots/Screenshot%202025-11-13%20192032.png "Online decoder for Rail Fence Cipher")

This confirmed that the message was successfully decoded.

### New Learnings

1. **Rail Fence Cipher is a transposition cipher**, meaning it rearranges characters rather than substituting them.
2. If the number of rails is known, decryption is very direct — simply plug in the rail count.
3. Challenge names and descriptions often give strong hints (in this case, “rail fence” and “4 rails”).
4. Classical ciphers are easy to break once the method and parameters (like rail count) are identified.

---

# Guess My Cheese

Try to decrypt the secret cheese password to prove you're not the imposter!
Additional details will be available after launching your challenge instance.
