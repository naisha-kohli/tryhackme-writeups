# Windows Fundamentals Part 1

## Evolution of Windows

Microsoft Windows was first released in 1985 and has become the most widely used operating system for both personal and corporate environments. Due to its popularity, Windows has always been a major target for hackers and malware authors.

### Major Windows Versions (Chronological Order)

| Version       | Release Year | Notes                                                                 |
| ------------- | ------------ | --------------------------------------------------------------------- |
| Windows XP    | 2001         | Very popular and widely adopted                                       |
| Windows Vista | 2007         | Major redesign but suffered from performance and compatibility issues |
| Windows 7     | 2009         | Stable, reliable, and widely accepted successor to Vista              |
| Windows 8     | 2012         | Introduced a touch-focused interface that many users disliked         |
| Windows 8.1   | 2013         | Improved Windows 8 but failed to gain widespread popularity           |
| Windows 10    | 2015         | Combined familiarity with modern features and improved security       |
| Windows 11    | 2021         | Current desktop operating system with a redesigned user interface     |

---

## Windows Vista

Windows Vista introduced significant changes to the Windows operating system. However, it faced performance issues, hardware compatibility problems, and poor user reception. As a result, it was quickly replaced by Windows 7.

---

## Windows 7

Windows 7 became one of Microsoft's most successful operating systems due to its stability, performance, and ease of use. Businesses and home users widely adopted it after the disappointment of Windows Vista.

### Why Did Microsoft End Support for Windows 7?

Microsoft ended support for Windows 7 on January 14, 2020.

Reasons:

* New security threats required more advanced protections.
* Older operating systems are expensive to maintain.
* Modern hardware and software require newer operating systems.
* Microsoft wanted users to move to more secure versions of Windows.

After support ended, Windows 7 no longer received security updates, making it increasingly vulnerable to cyberattacks.

---
# Windows 10

Windows 10 addressed many of the criticisms of Windows 8 and became the standard operating system for businesses and home users.

### Key Improvements

* Return of the Start Menu
* Better performance and stability
* Regular security updates
* Improved hardware compatibility
* Enhanced malware protection
* Virtual desktops and productivity features
* Better support for modern applications

Microsoft announced that Windows 10 support will end on October 14, 2025.

---

## Windows 11

Windows 11 is the current desktop operating system from Microsoft.
### Features

* Modern user interface
* Improved security
* Better gaming performance
* Enhanced productivity tools
* Support for the latest hardware

---

## Windows File System (NTFS)

### NTFS (New Technology File System)
- NTFS stands for **New Technology File System**.
- It is the default file system used in modern Windows operating systems.
- Before NTFS, Windows used:
  - **FAT16/FAT32** – File Allocation Table
  - **HPFS** – High Performance File System

### Advantages of NTFS
- Supports files larger than **4 GB**.
- Can automatically repair file system errors using information stored in its **log file**.
- Allows **file and folder permissions**.
- Supports **compression** to save disk space.
- Supports **Encrypting File System (EFS)** for protecting data.

### NTFS Permissions
- Full Control
- Modify
- Read & Execute
- List Folder Contents
- Read
- Write

### Alternate Data Streams (ADS)
**Alternate Data Streams (ADS)** allow a file to contain **hidden additional data without changing the file's main content or filename**.

Example:
A file named `notes.txt` can secretly have another hidden stream attached to it that is not visible in File Explorer.

**Easy way to remember:**  
**ADS = Extra hidden data attached to a file.**

## Windows System32 Folder

### Windows Folder
- The **Windows** folder is usually located at:
  ```
  C:\Windows
  ```
- It contains the files required for the **Windows operating system**.
- Although it is commonly stored on the **C:** drive, it can also be installed on another drive or location.
- The system environment variable for the Windows directory is:
  ```
  %windir%
  ```

### System32 Folder
- **System32** is one of the most important folders inside the Windows directory.
- It contains **critical system files** required for Windows to function properly.
- Deleting or modifying files in the **System32** folder can make the operating system **unstable or even unable to boot**.

- ## User Accounts, Profiles, and Permissions

### Types of Local User Accounts

#### 1. Administrator
- Has **full control** over the system.
- Can:
  - Add or delete user accounts.
  - Modify user groups.
  - Change system settings.
  - Install or uninstall software.
  - Access and manage all files and folders.

#### 2. Standard User
- Has **limited permissions**.
- Can:
  - Use installed applications.
  - Create, edit, and delete their own files and folders.
  - Change some personal settings.
- **Cannot:**
  - Install most software that affects the whole system.
  - Add or delete user accounts.
  - Change important system settings.

### Managing Local Users and Groups

You can view and manage local user accounts using **Local Users and Groups**.

**Steps:**
1. Press **Win + R** to open the **Run** dialog.
2. Type:
   ```
   lusrmgr.msc
   ```
3. Press **Enter**.
4. The **Local Users and Groups** window will open, where you can:
   - View local user accounts.
   - Create or delete users.
   - Manage user groups.
   - Modify user account properties.



**Easy way to remember:**  
**`lusrmgr.msc` = Local Users and Groups Manager.**

## User Account Control (UAC)

### What is UAC?
**User Account Control (UAC)** is a Windows security feature that helps prevent **unauthorized changes** to the system.

### Why is UAC needed?
- Basic tasks like:
  - Browsing the internet
  - Using Microsoft Word
  - Watching videos
  - Editing personal files

  **do not require administrator privileges.**

- However, tasks like:
  - Installing software
  - Changing system settings
  - Modifying Windows files

  **require elevated (administrator) privileges.**

Without UAC, if malware infects a computer while you're logged in as an administrator, it could make system-wide changes without asking for permission.

### How UAC Works
- Even if you log in with an **Administrator** account, Windows does **not** run everything with full administrator privileges.
- When an action requires higher privileges, Windows displays a **UAC prompt** asking for confirmation.
- The action only proceeds if the user approves it.

> **Note:** UAC does **not** apply to the built-in **Administrator** account because it already runs with full privileges.

### Example
Suppose you download and install **Google Chrome** or **Visual Studio Code**.

When you run the installer, Windows displays a message like:

> **"Do you want to allow this app to make changes to your device?"**

If you click **Yes**, Windows temporarily grants administrator privileges to complete the installation.

### Easy way to remember
**UAC = Windows asks, "Are you sure?" before allowing important system changes.**

## Task Manager

**Keyboard Shortcut:**
```
Ctrl + Shift + Esc
```

### What is Task Manager?
Task Manager is a Windows utility used to **monitor and manage running applications, processes, and system performance**.

### Information Available
- Running apps and background processes
- CPU, Memory, Disk, Network, and GPU usage
- Startup applications
- Logged-in users
- Running services




