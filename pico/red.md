# RED
## Description
RED, RED, RED, RED
## Steps
Upon downloading the image, i suspected that it was steganography because we are given a png image. \
At first i used exiftool to see its metadata and there was something interesting that caught my attention. \
There was a poem inside the metadata, but nothing more than that, so i used zsteg to look further.

```bash
zsteg -a red.png
```
<img width="1218" height="815" alt="image" src="https://github.com/user-attachments/assets/d1426d8a-4bcf-44c9-895e-f12e02604e78" />

> [!NOTE]
> the -a means that we force the zsteg tools to use all of its utility to scan the image

As you can see, there seems to be base64 strings that we can decrypt \
<img width="863" height="93" alt="image" src="https://github.com/user-attachments/assets/67585256-0a07-42d0-843a-cdc73b2e5b2d" />

Turns out that it really is the flag! \
```picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}```
