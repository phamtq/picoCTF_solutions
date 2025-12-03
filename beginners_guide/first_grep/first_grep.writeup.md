# [The Beginner's Guide to the picoGym] : First Grep

## Challenge
![12th challenge: Can you find the flag in the file? This would be really tedious to look through manually, something tells me there is a better way. The flag is in this file.](images/first.grep_challenge.png)

## Status

![Status Image](images/slayed.gif)

## Approach
For this challenge all you have to do is run the `grep` command on the downloaded file (`file`). You can use `cat` and the pipe it into `grep` or do it directly is fine. Either way is fine despite what others might say.

```bash
$ grep pico ./file
JUNK... picoCTF{grep_is_good_to_find_things_cEDf1591} ... JUNK
```

I'm not copying the entire output of `grep` as it's just full of junk.

## Solution
1.  Run the `grep` command on the file
2.  Find the flag

## Lessons
None.