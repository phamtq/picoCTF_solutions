# [The Beginner's Guide to the picoGym] : strings it

## Challenge
![11th challenge: Can you find the flag in file without running it?](images/insp3ct0r_challenge.png)

## Status

![Status Image](images/slayed.gif)

## Approach
Well, well, well. Would you look at that! If you've been following along with the previous challenges, you've got the solution to this one. Navigate to where you downloaded the file and run:

```bash
$ strings ./strings | grep pico
picoCTF{5tRIng5_1T_dB2CEA76}
```

## Solution
1.  Run the `strings` command on the downloaded file
2.  Look for the flag

## Lessons
None.