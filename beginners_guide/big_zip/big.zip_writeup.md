# [The Beginner's Guide to the picoGym] : Big Zip

## Challenge
![21th challenge: Unzip this archive and find the flag.](images/big.zip_challenge.png)

## Status
![Status Image](images/slayed.gif)

## Approach
Let's start by unzipping the file:

```sh
$ unzip big-zip-files.zip
<Lots of TXT files in a lot of directories>
```

It's clear that there are too many files to search through manually so there must be a way to look at a lot of them in an automated way. Using the lesson we learned from the previous challenge, let's start with something simple. Is there a file that contains the work `pico` in the filename?

```sh
$ find . \  grep pico
<Blank, no results>
```

So it looks like it might be in the file contents itself. Is there a Linux command utility that can search the contents of a file? A web search shows that our good friend `grep` has that ability. Such a handy tool! This StackOverflow [post](https://stackoverflow.com/questions/16956810/find-all-files-containing-a-specific-text-string-on-linux) shows us what to do:

```sh
$ grep -rn 'picoCTF_solutions/beginners_guide/big_zip/files' -e 'pico'
picoCTF_solutions/beginners_guide/big_zip/files/big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:1:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```

And that's our flag!

## Solution
1.  Unzip the downloaded file
2.  Run the `grep` command with the appropriate options (see above)
3.  Submit the flag to the website

## Lessons
`grep` contains a whole lot of more advanced search features including, but not limited to, traversing a directory tree recursively to find the files that contain a particular search pattern.
