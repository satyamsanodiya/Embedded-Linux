# Linux Basic Commands for Embedded Systems

## Objective

To learn the fundamental Linux commands required for working with embedded Linux platforms such as the Raspberry Pi Zero 2W.

## Hardware Platform

- Raspberry Pi Zero 2W
- Raspberry Pi OS

## Commands Learned

### 1. pwd

**Purpose**

Displays the current working directory.

**Example**

```bash
pwd
```

**Typical Output**

```text
/home/pi
```

---

### 2. ls

**Purpose**

Lists files and directories in the current location.

**Example**

```bash
ls
```

---

### 3. ls -l

**Purpose**

Displays detailed information about files and directories.

**Example**

```bash
ls -l
```

Information displayed includes:

- File permissions
- Owner
- File size
- Modification date

---

### 4. mkdir

**Purpose**

Creates a new directory.

**Example**

```bash
mkdir test_directory
```

---

### 5. rmdir

**Purpose**

Removes an empty directory.

**Example**

```bash
rmdir test_directory
```

---

### 6. nano

**Purpose**

A lightweight terminal-based text editor used for creating and editing files.

**Example**

```bash
nano notes.txt
```

Common shortcuts:

| Shortcut | Function |
|-----------|----------|
| Ctrl + O | Save File |
| Ctrl + X | Exit Editor |
| Ctrl + K | Cut Line |
| Ctrl + U | Paste Line |

---

## Practical Activity Performed

- Connected to Raspberry Pi through SSH.
- Navigated the Linux file system.
- Created directories.
- Removed directories.
- Opened and edited files using Nano editor.

---

## Learning Outcome

Successfully learned the basic Linux commands required for file management and text editing on Raspberry Pi Zero 2W.

These commands form the foundation for future Embedded Linux development, including software deployment, shell scripting, device configuration, and application development.
