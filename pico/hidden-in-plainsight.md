# Hidden In Plainsight

## Description
You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag.

### Steps
### 1. First, i downloaded the jpg image
### 2. Check with Exiftool
because the description is "hidden in plainsight" i checked the image metadata right away with exiftool
```bash
exiftool img.jpg
```
and the output contains base64-encoded string which caught my attention

### 3. Decrypt the base64
i decrypt it with the command
```bash
"echo "c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9" | base64 -d
```
which then proceed to print out two words, that is: **steghide:cEF6endvcmQ=**\
and... i got another base64-encoded string so i proceed to decrypt it once again
after decrypting it, i got a passphrase ```pAzzword```
### 4. Extracting embedded file
i figured that if i got a password, there must be something hidden in the image file
```bash
steghide extract -sf img.jpg -p pAzzword
```
and just like that i got a file named flag.txt
### 5. Reading flag.txt
with the **cat** command, i succesfully extracted the flag ```picoCTF{h1dd3n_1n_1m4g3_92f08d7c}```
