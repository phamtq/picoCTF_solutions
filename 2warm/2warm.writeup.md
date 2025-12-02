# [The Beginner's Guide to the picoGym] : Obedient Cat

## Challenge
![5th challenge: What is 0x3D (base 16) in decimal (base 10)?](images/warmed.up_challenge.png)

## Status

![Status Image](images/slayed.gif)

## Approach
Now there's an easy way to convert it using a website or program but another way that requires a bit more brainpower is to use math. To convert the hex value of `0x3D` to a decimal number (base 10) count the number of characters after the `0x`, in this case 2. 

Then for each character, calculate `(X * 16^Y)`, where *X* is the numerical value of the first HEX character (0-9 and A-F being 0-15) and *Y* is it's position from right to left starting at zero. Then you add them all up.

In this case it would be:

> (3 * 16^1) + (13 * 16^0) = 61

So the flag would be `picoCTF{61}`.

## Solution
1.  Convert the hexidecimal value to a decimal value.

## Lessons
None.