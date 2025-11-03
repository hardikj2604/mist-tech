# Pondering Paths

## Implicit Relative Paths, from /

Now you're familiar with the concept of referring to absolute paths and changing directories. If you put in absolute paths everywhere, then it really doesn't matter what directory you are in, as you likely found out in the previous three challenges.

However, the current working directory does matter for relative paths.

- A relative path is any path that does not start at root (i.e., it does not start with /).
- A relative path is interpreted relative to your current working directory (cwd).
- Your cwd is the directory that your prompt is currently located at. This means how you specify a particular file, depends on where the terminal prompt is located.

Imagine we want to access some file located at /tmp/a/b/my_file.

- If my cwd is /, then a relative path to the file is tmp/a/b/my_file.
- If my cwd is /tmp, then a relative path to the file is a/b/my_file.
- If my cwd is /tmp/a/b/c, then a relative path to the file is ../my_file. The .. refers to the parent directory.

### Objective

Let's try it here! You'll need to run /challenge/run using a relative path while having a current working directory of /. For this level, I'll give you a hint. Your relative path starts with the letter c

### Solve

**Flag:** `pwn.college{cLaWuJ4GPaTWafYdnB_AQvPuqat.QX5QTN0wCO3UDOzEzW}`

-> In this challenge, we needed to get the flag from /challenge/run but without using absolute path.
-> Therefore first we executed the cd command to achieve the desired cwd of /
-> Then just execute the file using relative path that is challenge/run

```bash
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag: pwn.college{cLaWuJ4GPaTWafYdnB_AQvPuqat.QX5QTN0wCO3UDOzEzW}
```

### New Learning

1. A relative path does not begin with `/` and is interpreted relative to your current working directory (CWD).
2. The CWD matters for relative paths — if your CWD is `/`, then `challenge/run` refers to `/challenge/run`.
3. Absolute paths (start with `/`) always point to the same location no matter the CWD; relative paths are shorter and convenient when you are already in the right directory.
