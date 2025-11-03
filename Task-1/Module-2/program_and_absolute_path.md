# Pondering Paths

## Program and Absolute Paths

Let's explore a slightly more complicated path! Except for in the previous level, challenges in pwn.college are in the challenge directory and the challenge directory is, in turn, right in the root directory (/). The path to the challenge directory is, thus, /challenge. The name of the challenge program in this level is run, and it lives in the /challenge directory. Thus, the path to the run challenge program is /challenge/run.

### Objective

This challenge again requires you to execute it by invoking its absolute path. You'll want to execute the run file that is in the challenge directory that is, in turn, in the / directory. If you invoke the challenge correctly, it will give you the flag. Good luck!

### Solve

**Flag:** `pwn.college{kqtNJLz6Kk8I2ukavmGEtQ36-pH.QX1QTN0wCO3UDOzEzW}`

- Execute the challenge program using its absolute path by typing: /challenge/run

```bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{kqtNJLz6Kk8I2ukavmGEtQ36-pH.QX1QTN0wCO3UDOzEzW}
```

### New Learning

1. Absolute paths begin at the filesystem root (`/`). The challenge program lives at `/challenge/run`.
2. Invoking a program with its absolute path runs that exact program regardless of your current working directory.
3. Use absolute paths when a program is outside your PATH or when you want to avoid ambiguity from relative paths.
4. Solving this challenge reinforces the habit of running programs by full path when necessary (example: `/challenge/run`).
