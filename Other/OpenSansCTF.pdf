This CTF is a part of the WiCyS 2024 Scholarship Tier 1.
Unfortunately before I could conduct this Writeup after the challenge was over, the CTF challenges got locked. Here are a few of the memorable challenges.

**Fe01: contained a locked zip file.**
For this challenge I immediately knew that I would have to use some sort of password cracking tool. I am already familiar with using hashcat, but I learned that there was a way to run passwords against a zip file in john.
A simple google search of how to run john against a locked zip file quickly gave me instructions on how to do this
First I converted the zip file into a hash, john requires the password hash to be in a specific format, which can be done with zip2john fe01.zip > zip.hash
From this point on I was familiar with using wordlists and already had rockyou.txt downloaded. The simple command john - - rockyou.txt zip.hash quickly cracked the password which was starwars
The txt file inside of the zipped folder contained the flag

**be01 Buffer overflow**
I had learned about buffer overflow in theory but this was really fun to put into practice for this first time. This required me to nc into a server and then prompted me with a username. After entering a long string of characters I got “segmentation fault”, which from taking comptuer system knew it meant this challenge likely had something to do with memory overflow.
I had to guess and check with this, not the most sophisiticated method but I enterd in numbers. 20 - 100, eventually between getting segmentation faults and incorrect username outputs I was able to narrow down that the payload required 32 characters, which promptly got me the flag.


**ch01: Cryptography**
This was my favorite challenge of the whole CTF. I was given this string xhRmogZz9Nc2VuRUlhZG5lbkMtc3gyODA=OT, which immediately made me think Base64 as this is the only encoding that uses = signs as padding. I quickly noticed however that the = sign was not at the end.
First it made me thing ROT13 cipher, where i had to shift the = sign to the end or the beginning, however this did not work.
However my idea to try and move around the text to get the correct encoded form was right.
I then typed in Flag: and encoded this into base 64
I knew my desired output would be Flag: (something} so i typed in this into cyberchef
From here I quicly observed that xhRmogZz (the beginning of the string I was given) was very close to this output. By switching every two letters in the string


**ch02: Cryptography Again**
I was provided the following string “KgMCDFZPBhMvAxYYJRkGBxU8CgY8AwZGXl1QXV5laSYVTwUKAQYPEkwHAh0JTwEOCQFDGx4ADgICCg0fQE8UDgADTh8DQgcETB8GBBwDBksFAUMfBAYQSyEGBw8ACkM8CRwXDh4BQwgFGxpLCgARSxgHEQ4JTwQOAgoRChgGDAUfQUM/BApDKA0dEQobDhoYTA4RDkwcDAYJGwsCAghDBApPAksPAwIFQE8CBQhPFA5MBwIdCU8CSxgdAg8FGwoEAk8XAw0bQxwJjePyHgpDDwkcAA4CCwYPTAkRBAFPFwMJTyceBwoQSwMJQykZDAAHCRoAA0BPAR4YTxcDCU8CCBgaAgdMCQweAgsGGUwABUsBFkMHBQEGSxsOEEsBFkMMHg4NDwoOFwMJHYHr9RxDCR4AFwMJHU9LGwcMSw8ODg5MBwYZCU8KBUwJCg0YFk4EAgpPSx8KDR9MDkMYGQ0QHwUbFh8JTxcETBsLDkwsCh0FA0M8DR1PSw0BB0sfGwIZGAoHSxgHBksbBwwHCRwCBwlPCwoeCxQKHgpDCRkcCgUJHBBLGAcCH0wCGksKDhcDCR1DCA0dEQIJHEMEAk8XBAgOGkU=”
Again I knew that the = sign suggested base 64. I decoded this into cyberchef


From here I tried every iteration of base 64, and was pretty stuck from here. Then I got a hint that there was a “key”. This made me try multiple things like Vignere Cipher and eventually XOR cipher.
I noticed that the letters in the decoded base64 were OCKL which is an anagram for LOCK. The key was LOCK in XOR cipher.


Reflection: Overall I placed 164th out of 2000 people. I think this CTF has made me realize how far I have come in the past year. In my first CTF at my university I did not even know what netcat was, but here I found myself confidently using tools like Burpsuite, SQL Injections, Wireshark, and Cyberchef, and understanding quickly what my attack vector was! Unfortunately I was not able to do any challenges on the last day because of school work, so I feel I could have placed a little higher but overall it was so much fun and so encouraging to see how far I have come in the past year.
