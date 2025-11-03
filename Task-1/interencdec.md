# Interencdec

Can you get the real meaning from this file.
The file contains this :
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyMHdNakV5TnpVNGZRPT0nCg==

In the hint we are given that "Engaging in various decoding processes is of utmost importance"

### Solve

**Flag:** `picoCTF{caesar_d3cr9pt3d_f0212758}`

After seeing the text in the file it was encoded in some cipher i first thought that it is a Vigenère cipher but it was not then i assumed it to be a Base64 encoding and got `b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX20wMjEyNzU4fQ=='`

![Base64 Decoder](./screenshots/base64.png "Online decoder for Base64")

then if we again decode this after removing b' with base64 it gave `wpjvJAM{jhlzhy_k3jy9wa3k_m0212758}` which seem really like our flag format so i got a validation that i am on the right track then it looked like the caeser cipher as we have seen in previous ctf challenge

![Base64 Decoder](./screenshots/base64_2.png "Online decoder for Base64")

i tried bruteforcing for the flag as we did not have the key. and finally we got the flag by this method.

![Caeser Decoder](./screenshots/caeser.png "Online decoder for Caeser Cipher")

### New Learnings

1. Sometimes we have to decode some cipher multiple times and multiple ciphers can be applied to one target.

2. We may also have to remove few characters from the cipher to reach to the final message.

3. If we don't have the key for caeser cipher we may to go for the bruteforce method in which we will check for key 1 to 26.
