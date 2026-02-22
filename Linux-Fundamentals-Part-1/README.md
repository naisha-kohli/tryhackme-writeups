# Linux Fundamentals Part 1

## Room Overview
This room covers the basics of Linux including navigation, file system structure, and common terminal commands.

---
## Commands Practiced

| Command | Purpose |
|----------|----------|
| pwd | Shows current working directory |
| ls | Lists files and directories |
| ls -la | Shows hidden files |
| cd | Changes directory |
| cat | Displays file contents | (cat directory/file)
| man | Opens manual page |
| clear | Clears terminal |
| echo | output any text that we provide |
| whoami | Find out what user we're currently logged in as |
| pwd | print working directory |

## Search for files

| find -name file.txt | finds the location of the file | (when file name is known)
| find *.txt | (when only extention is known)
| grep | search for specific text (patterns) inside files | grep "word" filename

## Shell Operators
Shell operators are special symbols in Linux used to control how commands execute and how their input or output is handled.

| & | This operator allows you to run commands in the background of your terminal | sleep 10 & | (sleep 10 usually takes 10 seconds, but with & operator it will run in the background)
| && | to make a list of commands to run | ls && pwd | (pwd will take place only after ls )
| > | output redirector | (echo hey > note.txt)
| >> | appends the output rather than replacing | ( echo hi >> note.txt)


