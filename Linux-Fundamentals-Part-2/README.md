| Command | Purpose |
|--------|--------|
| mkdir | create directory/ folder |
| touch  | create file |
| cp | copy a file / folder |
| rm  | remove a file/ folder |
| file | determine the type of file |

## 📁 Common Linux Directories

| Directory | Description | Simple Idea |
|----------|------------|------------|
| `/tmp` | Stores temporary files created by programs. These files are usually deleted automatically. | Temporary storage (can be cleared anytime) |
| `/root` | Home directory of the root (admin) user. | Admin’s personal folder |
| `/var` | Contains data that changes frequently like logs, cache, and databases. | Changing/variable data |
| `/etc` | Stores system configuration files and settings. | System settings/control panel |

## 🔐 Understanding File Permissions (Numeric Format)

In Linux, file permissions control who can access a file and what actions they can perform.

There are three types of users:

- **Owner (u)** → The user who owns the file  
- **Group (g)** → A group of users  
- **Others (o)** → Everyone else  

---

### 📖 Permission Types

Each permission has a numeric value:

| Permission | Symbol | Value |
|-----------|--------|-------|
| Read      | r      | 4     |
| Write     | w      | 2     |
| Execute   | x      | 1     |

---

### 🔢 How Numeric Permissions Work

Permissions are represented by three digits:


- Owner → Read & write  
- Group → Read only  
- Others → Read only  

---

#### 🔹 700


| User   | Permissions | Meaning |
|--------|------------|--------|
| Owner  | 7 (4+2+1)  | Read, Write, Execute |
| Group  | 7 (4+2+1)  | Read, Write, Execute |
| Others | 7 (4+2+1)  | Read, Write, Execute |

👉 Everyone has full access

---

### 📌 Common Permission Examples

#### 🔹 755

