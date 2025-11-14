# Bandit Level 2 -> 3

**Goal:** 
Find the password for Level 3 stored in a file named `--spaces in this filename--` located in the home directory. 

---

### Thought Process 
When I logged into `bandit2`, I ran the command `ls` and saw a file named `--spaces in this filename--`. At first, I tried it this way: `cat ./--spaces in this filename--`, but that didn't work at all. The terminal threw errors like `No such file or directory`. 

After reading the error carefully, I realized Linux thought I was trying to open three separate files: `./--spaces`, `in`, `this`, and `filename--`. This showed me that spaces separate arguments, so the shell saw each word as a different filename.
---

### Why it Worked
When I wrapped the entire filename in quotes, like this: 
> cat `"./--spaces in this filename--"` 
the terminal treated everything inside the quotes as one single argument. 

I also tested: 
> `cat ./--spaces\ in\ this\ filename--`
and that worked too because the backslashes escape the spaces. 

The password for level 3 appeared right away!

---

### Commands Used
- `ssh bandit2@bandit.labs.overthewire.org -p 2220`
- `ls` 
- `cat "./--spaces in this filename--"` 
- `exit` 

---

### Key Learnings 
- Linux treats spaces as argument separators 
- Quoting (`" "` or `' '`) tells the shell: "this is one item"
- You can also escape spaces with a backslash (`\`)
- Using `./` before filenames is helpful when they start with a dash or special character
- Reading error messages carefully usually points you to the fix

--- 

### Challenges / Notes 
I learned that spacing matters more than I expected on the command line. Also, double quotes are often easier to use than backslashes when a filename has lots of spaces. 

---

### Result 
Successfully retrieved the password from the `--spaces in this filename--` file and used it to log into `bandit3`. 