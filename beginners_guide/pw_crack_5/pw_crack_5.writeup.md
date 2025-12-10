# [The Beginner's Guide to the picoGym] : PW Crack 5

## Challenge
![19th challenge: Can you crack the password to get the flag? Download the password checker here and you'll need the encrypted flag and the hash in the same directory too. Here's a dictionary with all possible passwords based on the password conventions we've seen so far.](images/pw.crack.4_challenge.png)

## Status
![Status Image](images/slayed.gif)

## Approach
This time we aren't given a list of possible passwords. Instead we're giving a dictionary file (aptly named `dictionary.txt`) with it's 65K+ entries to get the flag. We're going to need to modify the code such that each entry in the dictionary is an element in an array.

```python
flag_enc = open('level5.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level5.hash.bin', 'rb').read()
with open('dictionary.txt', 'r') as file:
    passwords = [line.strip() for line in file] 
```

This takes the dictionary file, adds it to an array, and takes out the newline character (`\n`). If we don't take out the newline character, that'll be used to check against the password hash.

The rest of the program will be similar to th previous 2 challenges.

```python
def level_5_pw_check(pass_seq):
    #user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(pass_seq)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), pass_seq)
        print(decryption)
        return
    print("That password is incorrect")


for i in passwords:
    level_5_pw_check(i)
```

When we run this along with the `grep` command, we get:

```sh
$ python hack.py | grep pico
picoCTF{h45h_sl1ng1ng_36e992a6}
```

## Solution
1.  Put the contents of the dictionary file into an array
2.  Modify the Python code to use those passwords
3.  Grab the flag

## Lessons
How to loop through a file and add it to an array in Python while removing newline characters. 
