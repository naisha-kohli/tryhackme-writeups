Nano

It is easy to get started with Nano! To create or edit a file using nano, we simply use nano filename -- replacing "filename" with the name of the file you wish to edit.
✏️ Nano Text Editor
Nano is a simple and beginner-friendly text editor used in Linux. It allows you to create, edit, and view files directly from the terminal.
👉 It is widely used because it is easy to understand and does not require complex commands.

## ⌨️ Nano Key Commands

| Key Combination | Function         | Description                          |
|----------------|------------------|--------------------------------------|
| Ctrl + G       | Get Help         | Opens the help menu                  |
| Ctrl + O       | Write Out        | Saves the file                       |
| Ctrl + X       | Exit             | Closes the editor                    |
| Ctrl + W       | Where Is         | Searches for text                    |
| Ctrl + K       | Cut Text         | Cuts current line                    |
| Ctrl + U       | Paste Text       | Pastes text                          |
| Ctrl + J       | Justify          | Formats text                         |
| Ctrl + C       | Cursor Position  | Shows cursor location                |
| Ctrl + T       | Spell Check      | Runs spell checker                   |
| Ctrl + _       | Go To Line       | Jump to a specific line              |
| Alt + U        | Undo             | Undo last action                     |
| Alt + E        | Redo             | Redo last action                     |
| Alt + A        | Mark Text        | Start selecting text                 |
| Alt + 6        | Copy Text        | Copy selected text                   |

⚙️ Processes in Linux

A process is simply a program that is currently running on your computer.

👉 Example:

When you open a terminal → that is a process
When you run a command like nano → that becomes a process
🧠 What is the Kernel?

The kernel is the core part of the operating system.

👉 It acts like a manager:

Controls CPU, memory (RAM), and devices
Manages all running processes
Decides which process gets resources

💡 Simple idea:
👉 Kernel = Brain of the OS

🆔 What is PID (Process ID)?
Every process has a unique number called a PID
It helps the system identify and manage processes

👉 Example:

First process → PID 1
Next process → PID 2
And so on...

🔍 Viewing Processes
1️⃣ View Your Processes
ps
👉 Shows:

Running processes in your current session
PID, status, CPU usage, command name

2️⃣ View All Processes
ps aux

👉 Shows:

All system processes
Processes from other users
Background/system services

📈 Real-Time Process Monitoring
top

👉 This shows:

Live running processes
Updates automatically
CPU & memory usage in real-time

💡 Press q to exit


🔧 Managing Processes

You can control or stop processes using signals.

❌ Kill a Process
kill PID

Example:
kill 1337

🚦 Types of Signals
Signal	Meaning
SIGTERM	Stops process safely (default)
SIGKILL	Forcefully stops process
SIGSTOP	Pauses the process


🍰 How Processes Start (Simple Explanation)

When your system starts:

The kernel starts first
Then a special process starts called:

👉 systemd (on most Linux systems)

🧠 What is systemd?
It is the first main process (PID 1)
It manages all other processes

🔄 Starting Services on Boot (Simple Explanation)

Some programs (called services) need to run automatically when your system starts.

👉 Examples:

Web server (like Apache)
Database server
File server

Instead of starting them manually every time, we can tell Linux:

👉 “Start this program automatically when the system boots”

🧠 What is systemctl?

systemctl is a command used to control services in Linux.

It talks to a system called systemd (which manages all processes).'


⚙️ Foreground & Background Processes

In Linux, processes can run in two ways:

Foreground	Runs in terminal (you see output)
Background	Runs behind the scenes

🖥️ Foreground Example
echo "Hello"


👉 Output appears immediately in terminal

🔙 Background Example
echo "Hello" &


👉 Instead of output, you’ll see something like:

[1] 1234

1 → Job number
1234 → Process ID (PID)

💡 Why Use Background?
Run long tasks without waiting
Continue using terminal
Useful for scripts and file transfers

⏸️ Pause a Running Process

Press:

Ctrl + Z


👉 This will:

Pause the process
Send it to background

🔄 Resume Process (Foreground)
fg

👉 Brings process back to foreground

🔁 Resume in Background
bg

👉 Continues process in background
