# Hello Hackers

## Command History

You're going to type a lot of commands, and typing everything from scratch can be annoying. Luckily, the shell saves a history of every command you invoke.

You can scroll through those saved commands with the up/down arrow keys, and we'll practice that in this challenge. In other challenges, the history will contain the log of the commands you've run, so if you need to run a similar command again, you can use the arrow keys to scroll through and find it!

```
hacker@dojo:~$ echo Hello Hackers!
Hello Hackers!
hacker@dojo:~$
```

### Objective

This challenge will inject the flag into your history. Bring up a terminal, hit the up arrow, and grab it!

### Solve

**Flag:** `pwn.college{Quv6KL05YxZZ9Bxutrj_JFgnXyK.0lNzEzNxwCO3UDOzEzW}`

-> In this challenge, we were asked to get the flag by accessing the command history by pressing the up button.

```bash
hacker@hello~command-history:~$ the flag is pwn.college{Quv6KL05YxZZ9Bxutrj_JFgnXyK.0lNzEzNxwCO3UDOzEzW}
```

### New Learning

1. We can get the log of commands we have used which can be very usefull if use those commands frequently.
2. We can grab them by pressing the up arrow key.
