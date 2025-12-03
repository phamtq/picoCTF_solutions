# [The Beginner's Guide to the picoGym] : where are the robots

## Challenge
![13th challenge: Can you find the robots? http://fickle-tempest.picoctf.net:51886](images/where.are.the.robots_challenge.png)

## Status
![Status Image](images/slayed.gif)

## Approach
Using the title and description as a hint, I believe it's referring to Robot Exclusion Protocol. See this [Wikipedia entry](https://en.wikipedia.org/wiki/Robots.txt) for more information.

Since we're dealing with the `robots.txt` file. Let's try appending that to the end of the URL (`http://fickle-tempest.picoctf.net:51886/robots.txt`). This shows us in the web browser:

```
User-agent: *
Disallow: /cc6b1.html
```

That HTML file looks interesting! Let's try append that to the original URL (`http://fickle-tempest.picoctf.net:51886/cc6b1.html`).

And what do you know! There's the flag (`picoCTF{ca1cu1at1ng_Mach1n3s_cc6b1}`)!

## Solution
1.  Go to the website
2.  Append `/robots.txt` to the end of the URL
3.  Append `/cc6b1.html` to the end of the original URL

## Lessons
None.
