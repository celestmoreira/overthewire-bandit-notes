# Bandit Level 0 -> 1 

**Goal:** 
Find the password for Level 1 stored in a file named `readme` in the home directory. 

---

### Thought Process 
Started by connecting to the Bandit server using SSH on port 2220.
After logging in as `bandit0`, I explored the home directory and located a file named `readme`. 
I used `cat` to view its contents, which revealed the password for the next level. 

---

### Commands Used
- `ssh bandit0@bandit.labs.overthewire.org -p 2220`
- `ls` 
- `cat` `readme` 
- `exit` 

---

### Key Learnings 
- How to connect to a remote Linux server using SSH 
- How to list files in the current directory with `ls` 
- How view file contents using `cat`
- How to navigate basic Linux environments safely 

--- 

### Challenges / Notes 
At first, I wasn't sure which port to use, noted that it's always 2220 for Bandit.
Remebered to always log out with `exit` before connecting to the next level. 

---

### Result 
Successfully retrieved the password from the `readme` file and used it to log into `bandit1`. 