# [The Beginner's Guide to the picoGym] : 2warm

## Challenge
![6th challenge: Can you convert the number 42 (base 10) to binary (base 2)?](images/2warm_challenge.png)

## Status

![Status Image](images/slayed.gif)

## Approach
Here's another one dealing with numbers of different bases but this time we're converting a decimal number (base 10) to binary (base 2). To figure out this one, we can create the table below. Our goal is to use a combination of the numbers in the first row (64, 32, 16, etc...) such that when they're added together, it gives us our number, in this case `10`. 

You put a number `1` in the second row under the number if we want to include it in our summation. So in this case we do the following:

| 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|---|---|---|---|---|---|---|
|0|1|0|1|0|1|0|

Since `32`, `8`, and `2` give us our target number of `42`, then the binary representation is `0101010` (or extra/less zeros in front of the number depending on how big a memory space we're dealing with). 

Trying `picoCTF{0101010}` tells us that's incorrect so let's try `picoCTF{101010}`. And that did it!

## Solution
1.  Convert the decimal number (base 10) to binary (base 2) by setting up a binary table (seen above).

## Lessons
None.