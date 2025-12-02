# [The Beginner's Guide to the picoGym] : what's a net cat?

## Challenge
![3rd challenge: Using netcat (nc) is going to be pretty important. Can you connect to fickle-tempest.picoctf.net at port 65495 to get the flag?](images/whats.a.net.cat_challenge.png)

## Status

![Status Image](images/slayed.gif)

## Approach
I haven't used the `netcat` program much in the past so I had to take a refresher.  A quick Google search showed the most basic way to use it:

```bash
$ nc fickle-tempest.picoctf.net 65495
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_f20a728c}
```

## Solution
1.  Connect to the server using the `netcat` program

## Lessons
The syntax for using `netcat` is:

```bash
$ netcat [options] host port
```

With the `[options]` being (to name a few), `-u` for a UDP connection and `-v` for verbose mode. 