# Cookie Monster Secret Recipe
## Description
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?
## Steps
After launching the web, fill in the username and password with random words.

<img width="574" height="205" alt="image" src="https://github.com/user-attachments/assets/8def5e88-6cc3-465c-aea2-ab77fb58dd88" />

It will give us a hint that we actually don't need to guess the password, it just needs cookies. \
So i hurriedly inspect the website again and go to the 'Application' tab, then search for cookies. \
Turns out there was a base64 string that we can decrypt.

<img width="981" height="817" alt="image" src="https://github.com/user-attachments/assets/0f010853-a121-4423-a252-8d77316af1f6" />

```bash
echo "cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzX0IzQUQ5NEMyfQ" | base64 -d 
picoCTF{c00k1e_m0nster_l0ves_c00kies_B3AD94C2}
```
And just like that, the flag has been successfully uncovered.
