# Pondering Paths

## Implicit Relative Path

In this level, we'll practice referring to paths using . a bit more.

Linux explicitly avoids automatically looking in the current directory when you provide a "naked" path. Consider the following:

```
hacker@dojo:~$ cd /challenge
hacker@dojo:/challenge$ run
```

This will not invoke /challenge/run. This is actually a safety measure: if Linux searched the current directory for programs every time you entered a naked path, you could accidentally execute programs in your current directory that happened to have the same names as core system utilities! As a result, the above commands will yield the following error:

```
bash: run: command not found
```

We'll explore the mechanisms behind this concept later, but in this challenge, we'll learn how to explicitly use relative paths to launch run in this scenario. The way to do this is to tell Linux that you explicitly want to execute a program in the current directory, using . like the previous levels.

### Objective

This challenge will need you to run it from the /challenge directory. Here, things get slightly tricky.

### Solve

**Flag:** `pwn.college{kTdEuguL5fvKw2hKKb3s5V_Kx2v.QXxUTN0wCO3UDOzEzW}`

-> In this challenge, we needed to execute the file run using explicit relative path but from the /challenge directory as the cwd.
-> So we cd into the /challenge directory then execute the ./run command to get the flag.

```bash
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{kTdEuguL5fvKw2hKKb3s5V_Kx2v.QXxUTN0wCO3UDOzEzW}
```

### New Learning

1. The shell does not automatically search the current directory for executables when you type a naked command name; this is a safety feature to avoid accidentally running local files instead of system utilities.

2. To explicitly run a program that lives in the current directory, prefix it with `./` (for example, `./run`) — this tells the shell you mean the file in the CWD.
