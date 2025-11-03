# Pondering Paths

## The Root

Alright, so the filesystem starts at /. Under that, there are a whole mess of other directories, configuration files, programs, and, most importantly, flags. In this level, we've added a program right in /, called pwn, that will give you the flag. All you need to do for this level is to invoke this program!

You can invoke a program by providing its path on the command line. In this case, you'll be giving the exact path, starting from /, so the path would be /pwn. This style of path, one that starts with the root directory, is referred to as an "absolute path".

### Objective

Start the challenge, launch a terminal, invoke the pwn program using its absolute path, and Capture that Flag! Good luck!

### Solve

**Flag:** `pwn.college{0ol4LOBby7yVRsn_ywVNOrCamKK.QX4cTO0wCO3UDOzEzW}`

-> In this challenge, we needed invoke pwn named programe by providing its path and get the flag

```bash
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{0ol4LOBby7yVRsn_ywVNOrCamKK.QX4cTO0wCO3UDOzEzW}
```

### New Learning

1. File system starts at /. It is root directory.
2. We can invoke any programe by executing its exact path as /pwn in this case.
3. The style of path, one that starts with the root directory, is referred to as an "absolute path".
