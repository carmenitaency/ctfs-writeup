# Binary Search
## Description
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.
Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools! 
## Steps
When i first launched the shell, it wants me to guess a number between 1 - 1000. \
The hint suggested that i try from the number 500 so i did just that.
If it says 'Higher! Try again.' then i will have to guess it higher.
If it says 'Lower! Try again.' then i will have to do the opposite.

I did this challenge manually, so i always halve the number from my last guess. \
For example: If i guess 500 and the shell wants me to go higher, i would guess 750 and so on and so forth.
```bash
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 550
Lower! Try again.
Enter your guess: 500
Higher! Try again.
Enter your guess: 530
Higher! Try again.
Enter your guess: 540
Lower! Try again.
Enter your guess: 535
Higher! Try again.
Enter your guess: 537
Higher! Try again.
Enter your guess: 539
Congratulations! You guessed the correct number: 539
Here's your flag: picoCTF{g00d_gu355_1597707f}
Connection to atlas.picoctf.net closed.
```
