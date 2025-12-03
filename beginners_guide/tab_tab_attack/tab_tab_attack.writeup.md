# [The Beginner's Guide to the picoGym] : Tab Tab Attack

## Challenge
![9thth challenge: Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: Addadshashanammu.zip](images/tab.tab.attack_challenge.png)

## Status

![Status Image](images/slayed.gif)

## Approach
This is a simple challenge to show you how to use the TAB autocomplete. But to make it more interesting, let's try another approach. You could unzip the file and copy and paste the last directory. That'd be much faster:

```bash
$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet
 
 $ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
```

Then run the following command (using Method #2 of the last challenge):

```bash
$ strings ./fang-of-haynekhtnamet | grep pico
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}
```

## Solution
1.  Unzip the file using the TAB key
2.  Navigate through the directories using the TAB key
3.  Run the `strings ./fang-of-haynekhtnamet | grep pico` command to get the flag

## Lessons
None.