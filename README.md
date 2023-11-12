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
## picoGYM keygenme-py challenge

We just have to find last part of the flag, which concated string of the certain indices of sha256 of the given word.
~~~
import hashlib

sername_trial = "SCHOFIELD"
bUsername_trial = b"SCHOFIELD"

key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"
key_part_dynamic1_trial = "xxxxxxxx"
key_part_static2_trial = "}"
key_full_template_trial = key_part_static1_trial + key_part_dynamic1_trial + key_part_static2_trial


indices = [4,5,3,6,2,7,1,8]

maybe_the_middle_part = ""

for i in indices:
	maybe_the_middle_part += hashlib.sha256(bUsername_trial).hexdigest()[i]


key = key_part_static1_trial + maybe_the_middle_part + key_part_static2_trial
print(key)
~~~
---
## picoGYM speeds and feeds challenge

On using netcat, there was a long list of code.
Then on looking at the hints and googling, i found that it was something called gcode used in the CNC machines or designing.
Then i looked for some gcode viewer and come across [NC viewer](https://ncviewer.com/), on pasting the code from nc we get the flag.

---
## picoGYM Shop Challenge

Since i have very little knowledge in reversing an ELF file, i looked at the hint and was just trying random cases in the program. 
Finally i found a probelm where we can by negative number items, so the more negative items we buy the more coins we get and i came up with 100 coins to buy the flag.
![image](https://github.com/varunadhityagb/picoCTF/assets/88021294/5c70dee7-da74-4697-9d3e-b58fb8ac001b)
Then on further running the following script to convert the given ascii values, the flag was found
~~~
flag_s = "112 105 99 111 67 84 70 123 98 52 100 95 98 114 111 103 114 97 109 109 101 114 95 53 57 49 97 56 57 53 97 125"
flag_sl = flag_s.split(" ")
flag = ""
for i in flag_sl:
	flag += chr(int(i))

print(flag)
~~~

---

