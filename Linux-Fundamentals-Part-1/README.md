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

| Command | Purpose |
|--------|--------|
| `find -name file.txt` | Finds the location of a file when the exact name is known |
| `find *.txt` | Finds files when only the extension is known |
| `grep "word" filename` | Searches for specific text (patterns) inside a file |


## Shell Operators
Shell operators are special symbols in Linux used to control how commands execute and how their input or output is handled.

| Operator | Purpose |
|----------|--------|
| `&` | Runs a command in the background (e.g., `sleep 10 &`) |
| `&&` | Runs multiple commands sequentially (next runs only if previous succeeds) |
| `>` | Redirects output to a file (overwrites existing content) |
| `>>` | Appends output to a file (does not overwrite existing content) |


