# Riddle Registry
## Description
Hi, intrepid investigator! 📄🔍 You've stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense.
But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered.
## Steps
For this challenge, i didn't really do anything special. Though i did the longer route first before doing the simpler way.\
I read the pdf file with the **cat** command and there's something that caught my attention in the Author field, it was a base64-encoded string.\
So i decrypt it and found the flag. But that's the long route because i had to scroll til the top to find the Author field.\
_"Lemme show you how the boss does it" - Phoenix_\
For the simpler way, i use exiftool to read the pdf's metadata
```bash
exiftool confidential.pdf
```
<img width="1107" height="398" alt="image" src="https://github.com/user-attachments/assets/47311723-5427-4746-a0cc-9d0a8081d65b" />\
As you can see, there's base64-encoded string on the Author's field.\
So i just decrypt it
```bash
echo "cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV9jYTc2YmJiMn0=" | base64 -d
```
and found the flag ```picoCTF{puzzl3d_m3tadata_f0und!_ca76bbb2}```

