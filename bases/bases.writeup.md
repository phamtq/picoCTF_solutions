# [The Beginner's Guide to the picoGym] : bases

## Challenge
![7th challenge: What does this bDNhcm5fdGgzX3IwcDM1 mean? I think it has something to do with bases.](images/bases_challenge.png)

## Status

![Status Image](images/slayed.gif)

## Approach
I've dealt with encoding like this before but let's try and take this from the perspective of someone who hasn't encountered something like this. After all, this activity wouldn't be much fun if I just ran through the solutions and told you, "Git gud. Figure it out yourself!". 

The description gives us a hint on how we should approach this. It mentions `bases` so we should start out investigation there. Compared to things we've learned thus far (see Warmed Up), it looks like the string of characters (`bDNhcm5fdGgzX3IwcDM1`) includes some that isn't allowed with hexidecimal like `G` and `z`.  

So maybe a way to get started is by doing a web search for other "bases". Using the idea that a lot of stuff in computers uses numbers like 4, 8, 16, etc... is there one that we haven't found that might include `z`? And since there are both capital and lowercase letters like in the case of `G`, is there one that can account for both of them? 

Now we know base 16 (hexadecimal) has `F` as it's highest value and that it's case doesn't matter. So let's try a number for bases higher than 16 that can include out critera (has numbers, can go to at least `z`, and includes upper and lowercase). 

Instead of trying every single number after 16, we can think about this logically. Does a hypothetical base 24 work? There are 26 letters in the Latin based alphabet so that might not fit. I say might because our string (`bDNhcm5fdGgzX3IwcDM1`) might not have numbers that go past `5` so that it can fit more letters or some other character. But even if we were to assume it ONLY includes the numbers `1`, `3` and `5`, it would still not be enough room.

If we look at something like base32, does that statisfy our criteria? Looking at the [Wikipedia entry for base32](https://en.wikipedia.org/wiki/Base32#Base_32_Encoding_per_%C2%A76), we see that the table allows for only capital letters and numbers 2 through 7. So that's not our base. How about base64?

That [Wikipedia entry](https://en.wikipedia.org/wiki/Base64#Alphabet) shows that it includes numbers (0-9), can go to at least `z`, and includes upper and lowercase). This might be it. Doing another search for a base64 converter we find there is one.

Let's put our string into one of them shows us a decoded message of `l3arn_th3_r0p35` or "learn the ropes" in [l33t](https://en.wikipedia.org/wiki/Leet) speak. Using the proper format of `picoCTF{l3arn_th3_r0p35}` we see that it's the solution to our challenge.


## Solution
1.  Decode the string using a base64 converter

## Lessons
There are many other encodings that I haven't run across before like base32. Interesting stuff!