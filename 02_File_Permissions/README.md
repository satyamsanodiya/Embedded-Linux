# Linux File Permissions

## Objective

Learn how Linux controls access to files and directories through permissions, ownership, and user privileges.

---

## Why File Permissions Matter

Linux is a multi-user operating system. File permissions protect files and directories from unauthorized access or modification.

In Embedded Linux systems, permissions are important for:

* Executing scripts
* Running applications
* Accessing device files
* Protecting system configuration files
* Managing services

---

## Viewing File Permissions

Use:

```bash
ls -l
```

Example:

```text
-rw-r--r-- 1 pi pi 120 Jun 4 notes.txt
```

---

## Understanding Permission Fields

Example:

```text
-rw-r--r--
```

Breakdown:

```text
-
rw-
r--
r--
```

### First Character

```text
-  = Regular File
d  = Directory
l  = Symbolic Link
```

### Owner Permissions

```text
rw-
```

Owner can:

* Read
* Write

Cannot:

* Execute

### Group Permissions

```text
r--
```

Group can:

* Read

Cannot:

* Write
* Execute

### Others Permissions

```text
r--
```

Everyone else can:

* Read

Cannot:

* Write
* Execute

---

## Permission Symbols

| Symbol | Meaning |
| ------ | ------- |
| r      | Read    |
| w      | Write   |
| x      | Execute |

---

## Changing Permissions

Use:

```bash
chmod
```

### Example

```bash
chmod 755 script.sh
```

Permission Breakdown:

```text
7 = 4 + 2 + 1 = rwx
5 = 4 + 1     = r-x
5 = 4 + 1     = r-x
```

Result:

```text
Owner  : Read + Write + Execute
Group  : Read + Execute
Others : Read + Execute
```

---

## Common chmod Values

| Value | Permission |
| ----- | ---------- |
| 777   | rwxrwxrwx  |
| 755   | rwxr-xr-x  |
| 700   | rwx------  |
| 644   | rw-r--r--  |
| 600   | rw-------  |

---

## File Ownership

View ownership using:

```bash
ls -l
```

Example:

```text
-rw-r--r-- 1 pi pi notes.txt
```

First "pi" = Owner

Second "pi" = Group

---

## Superuser (Root)

Linux has a special administrator account called:

```text
root
```

Root has permission to access and modify almost everything on the system.

---

## Using sudo

Execute commands with root privileges:

```bash
sudo apt update
```

Meaning:

```text
sudo = Super User Do
```

---

## Useful Commands

Check current user:

```bash
whoami
```

Example Output:

```text
pi
```

Check user information:

```bash
id
```

Example:

```text
uid=1000(pi) gid=1000(pi)
```

View groups:

```bash
groups
```

---

## Practical Exercises

### Create a File

```bash
nano test.txt
```

### View Permissions

```bash
ls -l
```

### Make File Executable

```bash
chmod 755 test.txt
```

### Verify Changes

```bash
ls -l
```

---

## Learning Outcome

After completing this section, I understand:

* Linux permission structure
* Read, Write, and Execute permissions
* Owner, Group, and Others concepts
* Numeric permission notation
* File ownership
* Root user privileges
* Usage of sudo for administrative tasks

These concepts form the foundation for Embedded Linux development, system administration, shell scripting, and Linux kernel work.
