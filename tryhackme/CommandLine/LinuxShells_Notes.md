# Room: Linux Shells (TryHackMe)

**Date:** 14 Sept 2025
**Path:** Cyber Security 101
**Goal:** Learn about different Linux shells, how to write basic shell scripts (loops, conditionals), and working with shell configuration & permissions.

## 1. Key Concepts Learned

* There are **different types of shells** in Linux, e.g. bash, dash, sh, zsh, etc. You can list them via `cat /etc/shells`. ([TryHackMe][1])
* Shell scripting basics: **loops**, **conditional statements** (if-then, case etc.).
* Script execution permissions: using `chmod +x` (making scripts executable).
* Interacting with a shell: commands, input/output, understanding the shell prompt etc.

## 2. Commands / Tools Practiced

* `cat /etc/shells` to see available shells.
* Writing simple scripts with loops and conditionals.
* Changing file permissions: `chmod +x script.sh`.
* Other shell basics: `ls`, `pwd`, `cd`, `echo`, etc.

## 3. Takeaways

* Knowing which shell is being used matters (syntax differences, built-in capabilities).
* Permissions are a key part of script security and usability (scripts must be executable).
* Loops and conditionals enable scripts to do more than just linear commands — logic / branching makes them powerful.

## 4. Next Steps

* Expand into more advanced scripting: functions, argument parsing, error handling.
* Explore shell startup files and configuration (e.g. `.bashrc`, `.profile`).
* Use more complex practical exercises: writing scripts to automate tasks or process logs.
