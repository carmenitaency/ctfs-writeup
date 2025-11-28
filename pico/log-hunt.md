# Log Hunt
## Description
Our server seems to be leaking pieces of a secret flag in its logs. The parts are scattered and sometimes repeated. Can you reconstruct the original flag?
## Steps
### 1. Like always, i downloaded the file attachment first
### 2. Using grep
Because im a beginner, im confused on what to do with the server.log file. Should i check the payload with wireshark? Should i check the metadata?\
So i looked at the hint and it says that i can grep the flag, so i did just that. I greped the server.log with the command
```bash
grep 'picoCTF' server.log
```
and i got this as an output\
<img width="609" height="228" alt="image" src="https://github.com/user-attachments/assets/a159f3be-d3a2-41a5-bd7c-a73ac473039e" />\
Like the description says, the flag is scattered into different parts.\
I read some writeups and it refreshed my memory a little bit about the **cat** command.\
You can use the **cat** command for many purposes:
```bash
# Reading the file content
cat file.txt
cat file.txt exam.txt

# Create or overwrite a file
cat > newstuff.txt

# Show lines number / formatting
cat -n file.txt # number all lines
cat -b file.txt # number non-blank lines
cat -s file.txt # squeeze multiple blank lines
cat -E file.txt # show $ at end of each line
cat -T file.txt # show TAB as ^I
cat -v file.txt # show non-printing chars

# Pipes and filter
cat file.txt | less
cat file.txt | grep 'keyword'
```
I got that cheatsheet from [Log Hunt-General Skills-picoCTF WriteUp](https://medium.com/@community.jkpsm/log-hunt-general-skills-picoctf-writeup-b71dccaf1035)\
(forgive me for i need to read some writeups on how to solve this challenge because i haven't picked up CTF in 3 months T_T)

I decided to grep the word INFO FLAGPART because i got some parts from that word
```bash
cat server.log | grep 'INFO FLAGPART'
```
<img width="614" height="720" alt="image" src="https://github.com/user-attachments/assets/68cddb00-b7c5-493b-afe5-ee30b46db2fe" />\
And bam! we successfully found the rest of the scattered flag. We can just ignore the duplicated parts.\
So the final flag is ```picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}```
