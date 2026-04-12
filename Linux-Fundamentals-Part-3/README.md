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


# ⏰ Cron Jobs & Crontab (Simple Explanation)

## 📌 What is Cron?

**Cron** is a system process in Linux that runs tasks automatically at scheduled times.

These tasks are called **cron jobs**.

---

## 📄 What is Crontab?

A **crontab** (cron table) is a special file where you define your scheduled tasks.

Each line in a crontab represents one task that will run automatically.

---

## 🧩 Crontab Format

Each cron job follows this format:

```
MIN HOUR DOM MON DOW CMD
```

| Field | Meaning                       |
| ----- | ----------------------------- |
| MIN   | Minute (0–59)                 |
| HOUR  | Hour (0–23)                   |
| DOM   | Day of Month (1–31)           |
| MON   | Month (1–12)                  |
| DOW   | Day of Week (0–6, Sunday = 0) |
| CMD   | Command to execute            |

---

## 🧠 Example

```
0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/
```

### 🔍 What this means:

* `0` → Run at minute 0
* `*/12` → Every 12 hours
* `* * *` → Every day, month, and weekday
* `cp -R ...` → Copy the Documents folder to backups

👉 So, this command **backs up files every 12 hours**.

---

## ⭐ Wildcard (`*`)

The asterisk `*` means **"any value"**.

Example:

* `*` in the month field → every month
* `*` in the day field → every day

👉 Use `*` when you don't care about that value.

---

## ✏️ How to Edit Crontab

Run this command in the terminal:

```
crontab -e
```

* Opens your crontab file
* Lets you add or edit cron jobs
* You can choose an editor like Nano

---
# 📦 Packages & Software Repositories (Simple Explanation)

## 📌 What is a Package?

A **package** is simply a piece of software (like a program or tool) that you can install on Linux.

---

## 🌐 What is a Repository?

A **repository (repo)** is like an online store or library where software packages are stored.

* Developers upload their software here
* You download and install it using commands

---

## ⚙️ What is APT?

**APT (Advanced Package Tool)** is the system used in Ubuntu to manage software.

With APT, you can:

* Install software
* Update software
* Remove software

---

## 📥 Installing Software

To install a package:

```
sudo apt install package-name
```

---

## ➕ Adding a Repository

Sometimes, software is not available in default repositories.
So, you need to add a **new repository**.

### Step 1: Add GPG Key (Security Check)

```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```

👉 This ensures the software is trusted and safe.

---

### Step 2: Add Repository File

Create a new file:

```
/etc/apt/sources.list.d/sublime-text.list
```

Add repository details inside it.

---

### Step 3: Update Package List

```
sudo apt update
```

👉 This tells your system about the new repository.

---

### Step 4: Install the Software

```
sudo apt install sublime-text
```

---

## ❌ Removing a Repository

You can remove a repository by:

* Deleting its file from:

```
/etc/apt/sources.list.d/
```

OR

```
sudo add-apt-repository --remove ppa:repository-name
```

---

## 🗑️ Removing Software

```
sudo apt remove package-name
```

---

# 📜 Maintaining Your System: Logs (Linux)

## 📌 What are Logs?

**Logs** are files that store important information about what is happening on your system.

They help you:

* Debug errors 🐞
* Monitor system activity 👀
* Investigate security issues 🔐

---

## 📂 Where are Logs Stored?

Most logs in Linux are stored in:

```
/var/log/
```

👉 This is the main directory for system logs.

---

## 🔍 How to View Logs

### 1. Using `ls` (List log files)

```
ls /var/log
```

👉 Shows all available log files.

---

### 2. Using `cat` (View entire file)

```
cat /var/log/syslog
```

👉 Displays the full log file (can be very long).

---

### 3. Using `less` (Best method)

```
less /var/log/syslog
```

👉 Allows you to:

* Scroll up/down
* Search inside logs (`/keyword`)

---

### 4. Using `tail` (Recent logs)

```
tail /var/log/syslog
```

👉 Shows the last few lines (latest activity).

---

### 5. Live Monitoring (Real-time logs)

```
tail -f /var/log/syslog
```

👉 Updates logs live as new entries are added.

---

## 📄 Common Log Files

| File                | Description                 |
| ------------------- | --------------------------- |
| `/var/log/syslog`   | General system activity     |
| `/var/log/auth.log` | Login & authentication logs |
| `/var/log/kern.log` | Kernel (core system) logs   |

---

## 🔐 Permission Note

Some logs require **sudo** to access:

```
sudo less /var/log/auth.log
```

---





---



