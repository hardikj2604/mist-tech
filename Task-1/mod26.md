# Mod 26

Cryptography can be easy, do you know what ROT13 is?
cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_uJdSftmh}

### Solve

**Flag:** `picoCTF{next_time_I'll_try_2_rounds_of_rot13_hWqFsgzu}`

As it is a ROT 13 Cipher we have to shift each letter by 13 places which can be done manually by substituting each letter by corresponding letter after 13 places.
We can take help of online decoders for doing this work of shifting letters by 13 places.

![ROT 16 Decoder](./onlinedecoder.png "Online decoder for ROT 16 Cipher")

### New Learnings

ROT13 cipher(read as - "rotate by 13 places") is a special case of the Ceaser cipher in which the shift is always 13.
So every letter is shifted 13 places to encrypt or to decrypt the message.

### References

https://www.geeksforgeeks.org/dsa/rot13-cipher/
