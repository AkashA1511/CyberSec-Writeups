
Room Link:
[TryHackMe | Linux Fundamentals Part 1](https://tryhackme.com/room/linuxfundamentalspart1)

# Introduction
**Question 1: Let's get started!**
- Answer: No answer needed.

# A Bit of Background on Linux
**Question 2: What year was the first release of a Linux Operating System?**
- Answer: 1991

# Interacting With Your First Linux Machine (In-Browser)
**Question 3: I've deployed my first Linux machine!**
- Answer: No answer needed.

# Running your First few commands

echo       🠊    Output any text we provide
whoami     🠊    Find out what user we're currently logged in as!` 

**Question 4: If you wanted to output the text "TryHackMe", what would our command be?**

-   Answer: echo TryHackMe

**Question 5: What is the username of who you're logged in as on your deployed Linux machine?**

-   Answer: tryhackme

# Interacting With the Filesystem!


`ls       🠊     listing
cd       🠊     change directory
cat      🠊     concatenate
pwd      🠊     print working directory` 

**Question 6: On the Linux machine that you deploy, how many folders are there?**

-   Answer: 4

**Question 7: Which directory contains a file?**

-   Answer: folder4

**Question 8: What is the contents of this file?**

-   Answer: Hello World!

**Question 9: Use the cd command to navigate to this file and find out the new current working current directory. What is the path?**

-   Answer: /home/tryhackme/folder4

# Searching for Files

Sometimes you may not find what you're looking for. You can use the `find` command. Suppose you're looking for passwords.txt file. Then the command will be:


`$ find -name passwords.txt` 

Again, if you have a big file and want to save your precious time, you should use `grep`. `grep` and `find` are important commands for a cyber security researcher.

**Question 10: Use grep on "access.log" to find the flag that has a Prefix of "THM". What is the flag?**

-   Answer: THM{ACCESS}

**Question 11: And I still haven't found what I'm looking for.**

-   Answer: No answer needed.

# An Introduction to Shell Operators

&       🠊  This operator allows you to run commands in the background of your terminal.
&&      🠊  This operator allows you to combine multiple commands together in one line of your terminal.
>       🠊  This operator is a redirector - meaning that we can take the output from a command (such as using cat to output a file) and direct it elsewhere.
>>      🠊  This operator does the same function of the > operator but appends the output rather than replacing (meaning nothing is overwritten).` 

**Question 12: If we wanted to run a command in the background, What operator would we want to run?**

-   Answer: &

**Question 13: If I wanted to replace the contents of a file named "passwords" with the word "password123", what would my command be?**

-   Answer: echo password123 > passwords

**Question 14: Now If I wanted to add "tryhackme" to this file named "passwords" but also keep "passwords123", what would my command be?**

-   Answer: echo tryhackme >> passwords

**Question 15: Now use the deployed Linux machine to put these into practice.**

-   Answer: No answer needed.

# Conclusions and Summaries

This was the first part of Linux fundamental. There is a long way to go. But this is a good start. You get a good hold of something if you know the basics. Happy Hacking!!!!!

**Linux Fundamentals Part 2 room link:** TryHackMe | Linux Fundamentals Part 2