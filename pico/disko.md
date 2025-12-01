# DISKO
## Description
Can you find the flag in this disk image?
## Steps
I noticed that the file attachment has a '.gz' extension so i assumed that we have to decompress it with the gunzip command
```bash
gunzip disko-1.dd.gz
```

After successfully decompressing it, the file name is now disko-1.dd\
Looking at the hint, i just need to find the flag with the strings command so i did just that
```bash
strings disko-1.dd | grep -i picoCTF
```
And the flag has been found ```picoCTF{1t5_ju5t_4_5tr1n9_c63b02ef}```
