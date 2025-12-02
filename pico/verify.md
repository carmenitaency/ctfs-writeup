# Verify
## Description
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.
ssh -p 59862 ctf-player@rhea.picoctf.net
Using the password 6dd28e9b. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
- Checksum: 03b52eabed517324828b9e09cbbf8a7b0911f348f76cf989ba6d51acede6d5d8
- To decrypt the file once you've verified the hash, run ./decrypt.sh files/<file>.
## Steps
After connecting to ```ssh -p 59862 ctf-player@rhea.picoctf.net``` and doing the requirements, i checked the content with ``ls`` \
it turned out that there were 2 files and 1 directory. It was checksum.txt, decrypt.sh, and files\
<img width="397" height="53" alt="image" src="https://github.com/user-attachments/assets/70c38aa2-533f-4fb6-bbcf-de49a50fa1a3" />

Because there's a file called checksum.txt, i decided to read it with **cat** command \
<img width="696" height="50" alt="image" src="https://github.com/user-attachments/assets/a4d18af3-95cb-4eb4-a039-648b8fbf8c7e" />

The point of the challenge is, i have to search the same hash that is given in the files directory to verify it. \
To do that, i can use the ```sha256sum (file name)``` or if it's inside directory, ```sha256sum (directory name)/*```

<img width="1372" height="47" alt="image" src="https://github.com/user-attachments/assets/8f4ac536-902c-4167-8c37-f3bb6e8f898f" />

To our knowledge, it turned out that the same hash is in a file named 00011a60.\
Because there's already a decrypt script, we can just use it with this command
```bash
./decrypt.sh files/00011a60
```
And there we have it, the flag ```picoCTF{trust_but_verify_00011a60}```



