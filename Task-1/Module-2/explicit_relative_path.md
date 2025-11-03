# Pondering Paths

## Explicit Relative Paths, from /

Previously, your relative path was "naked": it directly specified the directory to descend into from the current directory. In this level, we're going to explore more explicit relative paths.

In most operating systems, including Linux, every directory has two implicit entries that you can reference in paths: . and ... The first, ., refers right to the same directory, so the following absolute paths are all identical to each other:

- /challenge
- /challenge/.
- /challenge/./././././././././
- /./././challenge/././

The following relative paths are also all identical to each other:

- challenge
- ./challenge
- ./././challenge
- challenge/.

Of course, if your current working directory is /, the above relative paths are equivalent to the above absolute paths.

### Objective

This challenge will get you using . in your relative paths. Get ready!

### Solve

**Flag:** `pwn.college{E5hebDaQAwyI5rVWjv1JHcvvRbs.QXwUTN0wCO3UDOzEzW}`

-> In this challenge, it was not clear that we need to execute which file or command so first i tried the same path as last that is /challenge/run. It said i should first cd to / directory.
-> After cd to / i knew that now i just have to use explicit relative path and execute the file /challenge/run as ./challenge/run

```bash
hacker@paths~explicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{E5hebDaQAwyI5rVWjv1JHcvvRbs.QXwUTN0wCO3UDOzEzW}
```

### New Learning

1. The single dot `.` refers to the current directory. Prefixing a path with `./` (for example `./challenge/run`) explicitly references a file inside your CWD.

2. From `/`, the relative paths `challenge/run` and `./challenge/run` both resolve to `/challenge/run`; both are valid but `./` makes the intent explicit.
