This is my first time writing writeup about solved challenges, so it can be messy

# PDF Generator

### Description
Aku membuat sebuah web sederhana untuk membuat file PDF. Namun, aku agak khawatir jika terdapat bug, karena aku membuat web ini dalam 1 hari saja.\
_It has an attachment file called pdfgenerator_pdfgenerator-dist.zip and a sandbox link to start the challenge_

### Steps

At first i tried to open the link that points to sandbox where i can run the challenge. When i click 'Start', the website gave me port and that is 44977:1337.
I tried opening it and boom there it is the PDF Generator website that is said in the description.
Because i'm a newbie, i don't know what to do with it, so i shifted my focus to the attachment file.

I tried to unzip the file using unzip command\
<img width="500" height="272" alt="image" src="https://github.com/user-attachments/assets/b1f7b0da-2c07-4ce9-afde-b77e29ab1356" />

After unzipping it, i spotted something interesting... of course it's no other than a file named _flag.txt_.\
I read it with the **cat** command and boom, there's the flag\
**TCF{8cec9528a8166a9bc0ea222152f13120}**

I actually didn't expect the challenge to be this easy because i thought i have to exploit the PDF Generator website that is provided in the description.\
Or maybe you can exploit the website too, idk. Though i always have a principle of if there's an easy route, why would you want to find the hardest route?
