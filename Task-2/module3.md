# Comprehending Commands

## cat : not the command , but the command

One of the most critical Linux commands is cat. cat is most often used for reading out files, like so:

```
hacker@dojo:~$ cat /challenge/DESCRIPTION.md
One of the most critical Linux commands is `cat`.
`cat` is most often used for reading out files, like so:
```

Finally, if you give no arguments at all, cat will read from the terminal input and output it. We'll explore that in later challenges...

### Objective

In this challenge, I will copy the flag to the flag file in your home directory (where your shell starts). Go read it with cat!

### Solve

**Flag:** `pwn.college{Qf1s3BMMrLzlOmeew9UWb_79GNK.QXxcTN0wCO3UDOzEzW}`

-> We directly had to give the command cat file and get the flag

```
bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{Qf1s3BMMrLzlOmeew9UWb_79GNK.QXxcTN0wCO3UDOzEzW}
```

### New Learning

1. Cat command is for reading out files.

---

## Catting absolute paths

In the last level, you did cat flag to read the flag out of your home directory! You can, of course, specify cat's arguments as absolute paths:

```
hacker@dojo:~$ cat /challenge/DESCRIPTION.md
In the last level, you did `cat flag` to read the flag out of your home directory!
You can, of course, specify `cat`'s arguments as absolute paths:
...
```

### Objective

In this challenge, I will not copy it to your home directory, but I will make it readable. You can read it with cat at its absolute path: /flag.

### Solve

**Flag:** `pwn.college{M8XovfOTAw4bnaPub9DbJyD6VCu.QX5ETO0wCO3UDOzEzW}`

-> We directly had to give the command cat file and get the flag

```
bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{M8XovfOTAw4bnaPub9DbJyD6VCu.QX5ETO0wCO3UDOzEzW}
```

### New Learning

1. We can use absolute paths as arguements.

2. /flag is where the flag always lives in pwn.college, but unlike in this challenge, you typically can't access that file directly.

---

## More catting practice

You can specify all sorts of paths as arguments to commands, and we'll practice some more with cat.

### Objective

In this level, I'll put the flag in some crazy directory, and I will not allow you to change directories with cd, so no cat flag for you. You must retrieve the flag by absolute path, wherever it is.

### Solve

**Flag:** `pwn.college{8ul8FEpSDAb49110e0Qc0DQNw3L.QXwITO0wCO3UDOzEzW}`

-> We dont have to cd into different directory and directly use its absolute path given in the terminal.

```
bash
You cannot use the 'cd' command in this level, and must retrieve the flag by
absolute path. Plus, I hid the flag in a different directory! You can find it
in the file /lib/x86_64-linux-gnu/krb5/flag. Go cat it out **without** cding
into that directory!
hacker@commands~more-catting-practice:~$ cat /lib/x86_64-linux-gnu/krb5/flag
pwn.college{8ul8FEpSDAb49110e0Qc0DQNw3L.QXwITO0wCO3UDOzEzW}
```

### New Learning

1. We can use absolute paths as arguements.

2. /flag is where the flag always lives in pwn.college, but unlike in this challenge, you typically can't access that file directly.

---

## grepping for a needle in a haystack

Sometimes, the files that you might cat out are too big. Luckily, we have the grep command to search for the contents we need! We'll learn it in this challenge.

There are many ways to grep, and we'll learn one way here:

```
hacker@dojo:~$ grep SEARCH_STRING /path/to/file
```

Invoked like this, grep will search the file for lines of text containing SEARCH_STRING and print them to the console.

### Objective

In this challenge, I've put a hundred thousand lines of text into the /challenge/data.txt file. grep it for the flag!

HINT: The flag always starts with the text pwn.college.

### Solve

**Flag:** `pwn.college{s6PTjv6-DDgE-X--Ab94b0u5kUT.QX3EDO0wCO3UDOzEzW}`

-> We just have to give the normal command to grep the string which include pwn.college with the file location as argument.

```
bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{s6PTjv6-DDgE-X--Ab94b0u5kUT.QX3EDO0wCO3UDOzEzW}
```

### New Learning

1. We can find a particular string from a large file using grep command.

---

## Comparing files

When looking for changes between similar files, eyeballing them might not be the most efficient approach! This is where the diff command becomes invaluable.

diff compares two files line by line and shows you exactly what's different between them. For example:

```
hacker@dojo:~$ cat file1
hello
world
hacker@dojo:~$ cat file2
hello
universe
hacker@dojo:~$ diff file1 file2
2c2
< world
---
> universe
```

The output tells us that line 2 changed (2c2), with world in the first file (<) being replaced by universe in the second file (>).

Sometimes, when new lines are added, you'll see something like:

```
hacker@dojo:~$ cat old
pwn
hacker@dojo:~$ cat new
pwn
college
hacker@dojo:~$ diff old new
1a2
> college
```

This tells us that after line 1 in the first file, the second file has an additional line (1a2 means "after line 1 of file1, add line 2 of file2").

### Objective

Now for your challenge! There are two files in /challenge:

- /challenge/decoys_only.txt contains 100 fake flags
- /challenge/decoys_and_real.txt contains all 100 fake flags plus the one real flag

Use diff to find what's different between these files and get your flag!

### Solve

**Flag:** `pwn.college{8kVqmDvz_rIeQIrukr-CaLwE0Zb.01MwMDOxwCO3UDOzEzW}`

-> We have to give argument of both files to be comapared to the diff command.

```
bash
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
92a93
> pwn.college{8kVqmDvz_rIeQIrukr-CaLwE0Zb.01MwMDOxwCO3UDOzEzW}
```

### New Learning

1. We can compare two files and detect the change in these two files .

---

## Comparing files

So far, we've told you which files to interact with. But directories can have lots of files (and other directories) inside them, and we won't always be here to tell you their names. You'll need to learn to list their contents using the ls command!

ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided. Observe:

```
hacker@dojo:~$ ls /challenge
run
hacker@dojo:~$ ls
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$ ls /home/hacker
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$
```

### Objective

In this challenge, we've named /challenge/run with some random name! List the files in /challenge to find it.

### Solve

**Flag:** `pwn.college{43iWiwLpp2s_ZZ_zLUEM-w8utv9.QX4IDO0wCO3UDOzEzW}`\

-> First find the new name of the file then execute this file.

```
hacker@commands~listing-files:~$ ls /challenge
8051-renamed-run-19252  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/8051-renamed-run-19252
Yahaha, you found me! Here is your flag:
pwn.college{43iWiwLpp2s_ZZ_zLUEM-w8utv9.QX4IDO0wCO3UDOzEzW}
```

### New Learnings

1. we can check the files and sun directories in a particular directory using ls command and it can accept other locations as argument also.

## Touching files

Of course, you can also create files! There are several ways to do this, but we'll look at a simple command here. You can create a new, blank file by touching it with the touch command:

```
hacker@dojo:~$ cd /tmp
hacker@dojo:/tmp$ ls
hacker@dojo:/tmp$ touch pwnfile
hacker@dojo:/tmp$ ls
pwnfile
hacker@dojo:/tmp$
```

### Objective

It's that simple! In this level, please create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag!

### Solve

**Flag:** `pwn.college{MyZyF2FFd5WY2u0LGDeRXAPkdI9.QXwMDO0wCO3UDOzEzW}`

-> First we have to create two files using touch command then execute the /challenge/run file.

```
hacker@commands~touching-files:~$ touch /tmp/pwn /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{MyZyF2FFd5WY2u0LGDeRXAPkdI9.QXwMDO0wCO3UDOzEzW}
```

### New Learnings

1. To create new files we can use touch command also give path as argument.

## Removing Files

Files are all around you. Like candy wrappers, there'll eventually be too many of them. In this level, we'll learn to clean up!

In Linux, you remove files with the rm command, as so:

```
hacker@dojo:~$ touch PWN
hacker@dojo:~$ touch COLLEGE
hacker@dojo:~$ ls
COLLEGE     PWN
hacker@dojo:~$ rm PWN
hacker@dojo:~$ ls
COLLEGE
hacker@dojo:~$
```

### Objective

Let's practice. This challenge will create a delete_me file in your home directory! Delete it, then run /challenge/check, which will make sure you've deleted it and then give you the flag

### Solve

**Flag:** `pwn.college{MEiczw7ASFRCboXdfw1Z_4_Lapg.QX2kDM1wCO3UDOzEzW}`

-> Delete the file using the rm command and then execute the command to get the flag

```
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{MEiczw7ASFRCboXdfw1Z_4_Lapg.QX2kDM1wCO3UDOzEzW}
```

### New Learnings

1. To remove files we have to use rm command and give the file path as argument.
