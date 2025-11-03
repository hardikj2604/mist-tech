# Hello Hackers

## Intro to Commands

In this challenge, you will invoke your first command! When you type a command and hit enter, the command will be invoked, as so:

```
hacker@dojo:~$ whoami
hacker
hacker@dojo:~$
```

Here, the user executed the whoami command, which simply prints the username (hacker) to the terminal. When the command terminates, the shell once again displays the prompt, ready for the next command.

### Objective

In this level, invoke the hello command to get the flag! Keep in mind: commands in Linux are case sensitive: hello is different from HELLO.

### Solve

**Flag:** `pwn.college{wU0IXODXg2u_n-5fMCL9nGByu88.QX3YjM1wCO3UDOzEzW}`

-> In this challenge, we were asked to invke the hello command so i executed hello and as commands in linux are case sensitive I would have typed HELLO it would not have given me the flag.

```bash
hacker@hello~intro-to-commands:~$ hello
Success! Here is your flag:
pwn.college{wU0IXODXg2u_n-5fMCL9nGByu88.QX3YjM1wCO3UDOzEzW}
```

### New Learning

1. `whoami` command prints the username to the terminal.
2. Commands in linux are case sensitive.
