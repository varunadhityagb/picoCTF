# picoGYM Writeups
---
## picoGYM hideme challenge
At first i used ghex, but it gave no result. Then on further reading the question again i tried binwalk to extract the flag.png file.
After using binwalk i got another png file which had the flag.
---
## picoGYM So Meta challenge
As soon as i saw the challenge name, i figured out that it had something to do with the meta data of teh file.
I then used the exiftool to find that the flag was given in the artist field.
---
## picoGYM St3g0 challenge
The file is a png file and since the challenge was related to steganography i used the zsteg command and the flag was present in the output.
---

