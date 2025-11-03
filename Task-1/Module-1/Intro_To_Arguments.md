# Hello Hackers

## Intro to Arguments

Let's try something more complicated: a command with arguments, which is what we call additional data passed to the command. When you type a line of text and hit enter, the shell actually parses your input into a command and its arguments. The first word is the command, and the subsequent words are arguments. Observe:

```
hacker@dojo:~$ echo Hello
Hello
hacker@dojo:~$
```

In this case, the command was echo, and the argument was Hello. echo is a simple command that "echoes" all of its arguments back out onto the terminal, like you see in the session above.

Let's look at echo with multiple arguments:

```
hacker@dojo:~$ echo Hello Hackers!
Hello Hackers!
hacker@dojo:~$
```

In this case, the command was echo, and Hello and Hackers! were the two arguments to echo. Simple!

### Objective

In this challenge, to get the flag, you must run the hello command (NOT the echo command) with a single argument of hackers. Try it now!

### Solve

**Flag:** `pwn.college{UoeP070-t2Z6pxLUtbxrKMNvTGM.QX4YjM1wCO3UDOzEzW}`

-> In this challenge, we were asked to invoke the hello command with a single argument hackers so after executing i received the flag

```bash
hacker@hello~intro-to-arguments:~$ hello hackers
Success! Here is your flag:
pwn.college{UoeP070-t2Z6pxLUtbxrKMNvTGM.QX4YjM1wCO3UDOzEzW}
```

### New Learning

1. Echo is a simple command that "echoes" all of its arguments back out onto the terminal.
2. We can pass additional data with the command called argument it will be treated as input with the command.
