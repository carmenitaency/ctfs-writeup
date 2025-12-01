# Hashing
## Description
A company stored a secret message on a server which got breached due to the admin using weakly hashed passwords. Can you gain access to the secret stored within the server?
## Steps
Imagine we are downloading many files, and when that task is done, we want to see if the file has been modified or not by transmission error or malicious attacker.
We can do that by hashing. Once a hash function has been applied to a file, we will get a value that contains strings in a fixed length to identify our file.
Every hash value of a file is the same except if the file has been modified. For example, the hash value of the word "Hello123" and "Hello123." will be different
because one of them has a dot.

Looking at the hint, we are redirected into [The CTF Primer](https://primer.picoctf.org/#_hashing)
So i read the description where it explains hashing, and i found a very interesting challenge along the way.\
<img width="850" height="301" alt="image" src="https://github.com/user-attachments/assets/e23dc516-f2cc-4ae0-a342-f9afa4323950" /> \
Even though there isn't any correlation to this challenge, i tried it as well to further enhance my knowledge
- Trying the CTF Primer challenge\
I created scripts that can dehash, i know it's not possible because you can't do it, but in this script logic, it was to input the hash and then it will find the matching hash in the rockyou.txt file.
```bash
mport hashlib

def crack_hash():
    target_hash = input("Masukkan hash SHA256: ").strip()
    wordlist_path = input("Masukkan path wordlist (cth: rockyou.txt): ").strip()

    try:
        with open(wordlist_path, "r", errors="ignore") as wordlist:
            for password in wordlist:
                password = password.strip()

                hashed = hashlib.sha256(password.encode()).hexdigest()

                if hashed == target_hash:
                    print(f"[+] Password ditemukan: {password}")
                    return

        print("[-] Tidak ditemukan password yang cocok di wordlist.")

    except FileNotFoundError:
        print("File wordlist tidak ditemukan!")

if __name__ == "__main__":
    crack_hash()
```
I once read somewhere "do it with automation, or die trying" so i created scripts to ease my work.\
And just like that, i got the password by 'dehashing' it!
```bash
Masukkan hash SHA256: cd0894152aa5eec36ec79eb2bcb90ca40f056804530f40732b4957a496b23dc8
Masukkan path wordlist (cth: rockyou.txt): /usr/share/wordlists/rockyou.txt
[+] Password ditemukan: ariena
```

---
Back to our main challenge, i tried it with the same script yet it didn't work. It says that there are no matching password from the rockyou.txt file. So i was left with a confused feeling of 'what am i supposed to do now?'\
After doing some research, rather than using python script, i can also use JohnTheRipper to crack password.\
The first hash that we know is ```482c811da5d5b4bc6d497ffa98491e38```
So, i stored it in a file named answer.txt\
<img width="450" height="137" alt="image" src="https://github.com/user-attachments/assets/93be28f7-3dc8-45fb-9faa-22e8ae428f56" /> \
And then i used the john command\
<img width="600" height="265" alt="image" src="https://github.com/user-attachments/assets/9a2fa8e3-1872-4682-9814-b10b6a5353e2" /> \
It turned out that the hash for ```482c811da5d5b4bc6d497ffa98491e38``` is ```password123```
After i submit the password, it gave out an output like this
```bash
Flag is yet to be revealed!! Crack this hash: b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3
```
So, i did the same command like before, but this time i'm using sha1
<img width="600" height="258" alt="image" src="https://github.com/user-attachments/assets/203bff9d-3975-4be5-925f-13404b5ae969" /> \
Abracadabra, i found the password again, it is now ```letmein``` \
But the challenge is not done yet, it revealed i have to crack another hash!
```bash
Almost there!! Crack this hash: 916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745
```
So, i did the same thing again, but instead of sha1, i am now using sha256 as its format. \
<img width="600" height="273" alt="image" src="https://github.com/user-attachments/assets/668b894a-5608-4fa9-9aa4-c51b014ced36" /> \
And there you go, the flag has been found folks! \
<img width="600" height="102" alt="image" src="https://github.com/user-attachments/assets/541d11f2-ad84-4b50-9f71-3b08ec5d751a" /> \
```picoCTF{UseStr0nG_h@shEs_&PaSswDs!_eb2f8459}```





