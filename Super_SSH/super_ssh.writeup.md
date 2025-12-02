# [The Beginner's Guide to the picoGym] : Super SSH

## Challenge
![Second challenge: Using a Secure Shell (SSH) is going to be pretty important. Additional details will be available after launching your challenge instance.](images/super.ssh_challenge.png)

## Status

![Status Image](images/slayed.gif)

## Approach
This is also another simple one designed to make sure your system and the picoCTF infrastructre is working correctly.

All that's required is to use your SSH client to log into their server using a non-default port.

```bash
$ ssh ctf-player@titan.picoctf.net -p51822
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_8306c99d}
Connection to titan.picoctf.net closed.
``` 

## Solution
1.  Connect to the specified SSH server and use the supplied password.

## Lessons
None.
