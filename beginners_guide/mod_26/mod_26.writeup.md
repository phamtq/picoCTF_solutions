# [The Beginner's Guide to the picoGym] : Mod 26

## Challenge
![4th challenge: Cryptography can be easy, do you know what ROT13 is? cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_uJdSftmh}](images/mod.26_challenge.png)

## Status

![Status Image](images/slayed.gif)

## Approach
I've never encountered ROT13 before so doing a little bit of Googling shows that it is a simple substitution cipher that replaces a particular character with one 13 spots away. If the letter is Z, then it just looks around to the front (assuming Latin alphabet). It appears upper and lowercase letters are treated the same.

The scrambled text of:

> cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_uJdSftmh}

Gives the solution of `picoCTF{next_time_I'll_try_2_rounds_of_rot13_hWqFsgzu}`.

## Solution
1.  Convert the cipher text using the ROT13 algorithm. Or you know... just use a website that does it for you.

## Lessons
How the ROT13 cipher works and how it's an insecure cipher.