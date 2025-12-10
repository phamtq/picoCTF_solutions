# [The Beginner's Guide to the picoGym] : PW Crack 3

## Challenge
![17th challenge: Can you crack the password to get the flag? Download the password checker here and you'll need the encrypted flag and the hash in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.](images/pw.crack.3_challenge.png)

## Status
![Status Image](images/slayed.gif)

## Approach
Alright! Let's do this again except this time we've got a different variation on a theme. Opening up the source code file (`level3.py`) gives us:

```python
import hashlib

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()

def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()

def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")

level_3_pw_check()

# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]
```

Now, one option might be just trying each of the seven, four character passwords but that wouldn't really teach you anything other than brute forcing a solution. I mean we might have to in the end but let's see if we can find another way that let's us learn a bit more.

The program first runs the `level_3_pw_check()` function which asks the user for the correct password. That info is stored in the `user_pw` variable and sent off to the `hash_pw()` function. 

It looks like `bytearray()` creates a sequence of bytes and puts them into an array with byte values ` (8bits = 1 byte).` When it's created, it's empty as there are no parameters to the `bytearray()` function. 

The `.extend()` method is used to add things onto the end of a list of things like an array in our case. Since it's being paired with `pw_str.encode()` that's what's going to fill the empty byte array. 

It uses the `hashlib` Python library to perform [MD5](https://en.wikipedia.org/wiki/MD5) operations to produce a hash. Since the input is a bytearray, it's likely doing hashing function on that particular format.

Let's see if we can dig any information on the `level3.hash.bin` file. We can run the command:

```sh
$ file level3.hash.bin
level3.hash.bin: data
```

Okay, that didn't give us much help although we know it's not just a text file. Let's try using a program that's installed on a lot of Linux system called `xxd`:


```sh
$ xxd level3.hash.bin
00000000: 1b18 e131 6f92 18cc 5b05 3e1c ea28 e02e  ...1o...[.>..(..
```

Okay, this might be something. We get a HEX representation of the contents of the file. Since we know that each character is 4 bits and 8 bits make up a single byte, each set of two is one byte. Knowing what we know from our discussion on the bytearray, our goal might be to enter a password such that after all the MD5 operations are performed the bytearray matches `correct_pw_hash` which is `1b18e1316f9218cc5b053e1cea28e02e`.

But that's a extremely hard thing to do because these hash function are one way. That is, you can encode a word or message but you can't decode it back to it's original word(s) without unreasonable amount of effort (especially relative to this challenge). 

So in the end, it looks like we're going to need to try each of the passwords. One way we can do this is to modify the program. But first let's make a copy (just in case):

```sh
$ cp level3.py hack.py
```

Then let's change the code to this:

```python
import hashlib

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()

def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()

def level_3_pw_check(pass_seq):
    #user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(pass_seq)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), pass_seq)
        print(decryption)
        return
    print("That password is incorrect")

#level_3_pw_check()

# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]
for i in pos_pw_list:
    level_3_pw_check(i)
```

Now when we run it, it'll show:

```sh
That password is incorrect
That password is incorrect
That password is incorrect
That password is incorrect
That password is incorrect
That password is incorrect
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}
```

## Solution
1.  Manually enter the 7 passwords OR modify the program to try each possible password
2.  Enter the flag into the picoCTF site

## Lessons
The Python `bytearray()` and `hashlib` library functions.
