# Binary Search

- [Challenge information](#challenge-information)
- [Solution](#solution)
- [References](#references)
  
## Challenge information
```
Level: Easy
Tags: picoCTF 2024, General Skills, shell, browser_webshell_solvable, ls
Points: 100
Author: JEFFERY JOHN

Description:
Want to play a game? As you use more of the shell, you might be interested in how they work! 

Binary search is a classic algorithm used to quickly find an item in a sorted list. 
Can you find the flag? You'll have 1000 possibilities and only 10 guesses.

Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, 
and forensics. Practicing the fundamentals manually might help you in the future when you have to 
write your own tools!

You can download the challenge files here:
challenge.zip

ssh -p 55705 ctf-player@atlas.picoctf.net
Using the password 83dcefb7. Accept the fingerprint with yes, and ls once connected to begin. 
Remember, in a shell, passwords are hidden!

Hints:
1. Have you ever played hot or cold? Binary search is a bit like that.
2. You have a very limited number of guesses. Try larger jumps between numbers!
3. The program will randomly choose a new number each time you connect. You can always try again, 
   but you should start your binary search over from the beginning - try around 500. 
   Can you think of why?
```

## Solution
Just by looking at the challenge name and description, the challenge can be solved via [Binary Search](https://www.khanacademy.org/computing/computer-science/algorithms/binary-search/a/binary-search#:~:text=Binary%20search%20is%20an%20efficient,game%20in%20the%20introductory%20tutorial.)

1. Follow the instruction and connect with SSH
  ```bash
zuan-picoctf@webshell:~$ ssh -p 53581 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:53581 ([18.217.83.136]:53581)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:3: [hashed name]
    ~/.ssh/known_hosts:22: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:53581' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password:
 ```
2. Start with initial value of 500. Then, repeatedly dividing in half the value depending the random number is in 'Lower' or 'Higher' until you've narrowed down to the correct value to obtain the flag. 
  ```bash
  Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 250
Lower! Try again.
Enter your guess: 125
Lower! Try again.
Enter your guess: 63
Lower! Try again.
Enter your guess: 32
Higher! Try again.
Enter your guess: 48
Lower! Try again.
Enter your guess: 40
Lower! Try again.
Enter your guess: 36
Lower! Try again.
Enter your guess: 34
Congratulations! You guessed the correct number: 34
Here's your flag: picoCTF{<REDACTED>}
  ```

## References

- [Binary Search](https://www.khanacademy.org/computing/computer-science/algorithms/binary-search/a/binary-search#:~:text=Binary%20search%20is%20an%20efficient,game%20in%20the%20introductory%20tutorial.)
