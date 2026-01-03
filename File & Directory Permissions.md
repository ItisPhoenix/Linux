# File & Directory Permissions

Linux permissions control who can access files and directories and what they can do with them.

## 🔑 Permission Basics

| Symbol | Permission | Description | Octal Value |
| :---: | :--- | :--- | :---: |
| **r** | Read | Ability to open and view the file/directory contents. | **4** |
| **w** | Write | Ability to modify, delete, or rename the file/directory. | **2** |
| **x** | Execute | Ability to run the file as a program/script or enter a directory. | **1** |

## 🧩 Understanding the Permission String

When you run `ls -l`, you see a string like `drwxrwxrwx`. This is divided into 4 parts:

`d` `rwx` `rwx` `rwx`

1.  **File Type** (1st char):
    * `d`: Directory
    * `-`: Regular file
2.  **Owner** (Next 3 chars): Permissions for the user who owns the file.
3.  **Group** (Next 3 chars): Permissions for the group assigned to the file.
4.  **Others** (Last 3 chars): Permissions for everyone else.

### User Categories
* **u** = User (Owner)
* **g** = Group
* **o** = Other (Everyone else)
* **a** = All (Owner + Group + Other)

---

## 🛠 The `chmod` Command

The `chmod` (Change Mode) command is used to change access permissions.

### 1. Symbolic Mode
Uses letters and operators (`+` add, `-` remove, `=` set exact).

```bash
# Give Owner (user) Read, Write, and Execute
chmod u=rwx test.sh

# Give Group and Others Read, Write, and Execute
chmod go=rwx test.sh

# Remove Write and Execute from Group and Others
chmod go-wx test.sh

# Add Executable permission to the Group
chmod g+x test.sh

```

### 2. Octal (Binary) Mode

Uses numbers to represent permissions. You sum the values to get the desired permission set.

* **4** = Read
* **2** = Write
* **1** = Execute
* **0** = No permission

**Common Calculations:**

* `7` (4+2+1) = Read + Write + Execute
* `6` (4+2) = Read + Write
* `5` (4+1) = Read + Execute
* `4` = Read only

**Examples:**

```bash
# 444: Owner(4), Group(4), Others(4)
# Everyone has Read-only permission.
chmod 444 test.sh 

# 744: Owner(7), Group(4), Others(4)
# Owner has Full control (rwx); Everyone else has Read-only.
chmod 744 test.sh

```

---

## 📂 Directory & Recursive Permissions

Permissions can also be applied to Directories and applied recursively to everything inside them.

```bash
# Set permissions for a directory using Symbolic mode
# Sets User, Group, and Others to rwx
chmod ugo=rwx Test/

# Set permissions using Octal mode
# 644: Owner gets Read+Write; Group/Others get Read
chmod 644 Test/

# Recursive (-R)
# Gives 777 (Full permission) to the directory AND 
# all files/sub-folders inside it.
chmod -R 777 Test/

```

```

```
