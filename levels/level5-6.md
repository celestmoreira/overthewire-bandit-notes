# Bandit Level 5 -> 6

**Goal:** 
Find the password for Level 5 stored in the only *human readable* file inside the `inhere` directory.

---

### Thought Process 
Started by running the command `ls` and saw a folder called inhere. Went inside that folder using `cd inhere`. Ran `ls` again and saw a bunch of files named `file00`, `file01`, `file02`, etc. 

I tried opening one with `cat` just to see what it looked like, but all I saw were random symbols. 

The level instructions said the password was in the **only human readable file**, so I needed a way to figure out which file that was without checking each one manually. 

I wasn't sure what to do, so I searched online "how to check file type in linux terminal" and that's when I learned about the `file` command! It tells you what kind of data a file contains. 

---

### Why it Worked
When I ran `file ./*` it scanned every file in the folder and told me what type of data each one had. 

Most said things like "data" or "non-ASCII text" but one of them said "ASCII text", that means it's made up of normal human readable characters. 

I opened up that file using `cat` and the password was revealed. 
---

### Commands Used
- `ssh bandit4@bandit.labs.overthewire.org -p 2220`
- `ls` 
- `cd inhere` 
- `file ./*`
- `cat file07` 

---

### Key Learnings 
- "Human readable" files are text files that contain ASCII characters. 
- The `file` command tells you the type of content inside each file 
--- 

### Challenges / Notes 
I didn't know about the `file` command before this level, so I had to look it up. Once I understood what "human readable" meant, the rest made sense. 
---

### Result 
Found the only file labeled “ASCII text” using the `file` command, opened it with `cat`, and retrieved the password. Logged into bandit5 successfully!