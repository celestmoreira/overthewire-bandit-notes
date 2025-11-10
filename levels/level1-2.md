# Bandit Level 1 -> 2

**Goal:** 
Find the password for Level 2 stored in a file called `-` located in the home directory.

---

### Thought Process 
When I listed the files, I saw one named `-`. The first thing I tried was: `cat -`, but the terminal just froze. I realized later it wasn't frozen, it was waiting for input. So I googled and googled and learned that `-` usually means *standard input* or *standrard output*. So to make `cat` treat it as an actual filename instead of stdin, I needed to specify the path explicitly. That's when I tried `cat ./-` and the password appeared right away.

---

### Why it Worked
In Linux, the dash(`-`) is a *special argument* that tells many programs to read from standard input. By typing `cat ./-`, the `./` tells the shell:
> "Look for a file named `-` in the current directory, not a command line option" 
The `./` prefix forces cat to interpret the `-` as a literal filename rather than as an option or input stream. 

---

### Commands Used
- `ssh bandit1@bandit.labs.overthewire.org -p 2220`
- `ls` 
- `cat ./-` 
- `exit` 

---

### Key Learnings 
- `-` is shorthand for *standard input/output* in Unix systems 
- Prefixing with `./` tells the command to treat it as a file name
- Pressing Ctrl + C exits a command waiting for input (like `cat -`)
- Understanding *why* a command works is as important as getting it to work 

--- 

### Challenges / Notes 
I thought my terminal froze when I ran `cat -`, but it was actually waiting for input. Pressing Ctrl + C stopped it.

---

### Result 
Successfully retrieved the password from the `-` file and used it to log into `bandit2`. 

