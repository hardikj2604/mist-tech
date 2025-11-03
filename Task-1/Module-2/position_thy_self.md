# Pondering Paths

## Position Thy Self

The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:

```
hacker@dojo:~$ cd /some/new/directory
hacker@dojo:/some/new/directory$
```

This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current path that your shell is located at.

### Objective

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!

### Solve

**Flag:** `pwn.college{AmWiQkw0um_bqxTpmfWRWNk_50G.QX2QTN0wCO3UDOzEzW}`

-> In this challenge, we needed run the run file in the challenge folder but from a different path.
-> So When we run the /challenge/run command from the root directory we get the message about the directory from where we have to execute the command.
-> when we cd to that directory and execute the /challenge/run command we get the flag

```bash
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /usr/aarch64-linux-gnu/include/gnu directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /usr/aarch64-linux-gnu/include/gnu
hacker@paths~position-thy-self:/usr/aarch64-linux-gnu/include/gnu$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{AmWiQkw0um_bqxTpmfWRWNk_50G.QX2QTN0wCO3UDOzEzW}
```

### New Learning

1. Each process has a current working directory (CWD). Using `cd` (change directory) updates the CWD for your shell and other commands you run.

2. The shell prompt uses `~` to represent your home directory; remember that relative paths are interpreted from your current working directory whereas absolute paths start at `/`.
