# Bandit Level 3 -> 4

**Goal:** 
Find the password for Level 4 stored in a hidden file inside the `inhere` directory.

---

### Thought Process 
After logging into `bandit3`, I ran `ls` and saw a folder named `inhere`.  

I used `cd inhere` to go inside it and then ran `ls` again, but nothing showed up.  

I thought maybe I was in the wrong folder or that the file got deleted. Then I remembered reading somewhere that Linux hides files that start with (`.`). 

I looked it up and found out you can use the `-a` option with `ls` to show all files, including hidden ones. So I tried `ls -a` and found a file named `...Hiding-From-You`. 

I opened the file with the `cat` command and the password appeared!

---

### Why it Worked
The regular `ls` command only shows visible files. Hidden files in Linux always start with a `.`, it's part of the Unix convention to "hide" configuration files or system stuff from cluttering your view. 

Adding the `-a` flag means **show all files**, so it lists everything, even hidden ones. 

---

### Commands Used
- `ssh bandit3@bandit.labs.overthewire.org -p 2220`
- `ls` 
- `cd inhere` 
- `ls -a`
- `cat ...Hiding-From-You` 

---

### Key Learnings 
- Hidden files start with a `.` and don't show up with regular `ls`
- "a" in `-a` stands for *all*
- when something seems "missing" it might just be hidden 

--- 

### Challenges / Notes 
I got confused when `ls` showed nothing, I thought maybe the directory was empty. Now I know to check for hidden files whenever a directory looks suspiciously empty.
---

### Result 
Found the hidden file and read the password inside it. 