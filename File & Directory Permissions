# Linux File Management & Permissions Cheat Sheet

## 📂 Part 1: File Management

### Navigation
| Command | Description |
| :--- | :--- |
| `pwd` | **P**resent **W**orking **D**irectory. Shows current path. |
| `cd ..` | Step back to the parent (previous) directory. |
| `cd /etc` | Change directory to the absolute path `/etc`. |
| `cd ~` | Change directory to the current user's **home** directory. |

### Listing Files (`ls`)
* `ls` : List files in simple format.
* `ls -l` : List in **list** format (permissions, owner, size, date).
* `ls -a` : List **all** files (including hidden files starting with `.`).
* `ls -al` : Combination of list format + all files.
* `ls -lh` : List format with **human-readable** sizes (KB, MB, GB).
* `ls -lR Desktop/` : **Recursive** list (shows files in Desktop and all sub-folders).

### Creating & Viewing
* `touch test.txt` : Creates an empty file named `test.txt`.
* `mkdir Test` : Creates a directory named `Test`.
* `echo "Hello"` : Prints "Hello" to the terminal.
* `echo "Hello" > test.txt` : Redirects "Hello" **into** `test.txt` (overwrites content).
* `cat [file]` : Displays content of a file.
* `cat /etc/passwd > passwd.txt` : Saves content of `/etc/passwd` into `passwd.txt`.
* `whatis [command]` : One-line description of a command.

### Editors
* `nano` : Simple terminal text editor.
* `vim` : Complex, powerful text editor.

### Manipulation (Copy, Move, Remove)
* `cp file.txt Folder` : Copies `file.txt` to `Folder`.
* `mv file.txt Folder/` : **Moves** `file.txt` to `Folder`.
* `mv old.txt new.txt` : **Renames** `old.txt` to `new.txt`.

> ⚠️ **Warning:** Deleted files are usually not recoverable.

* `rm file.txt` : Removes a file.
* `rmdir Folder` : Removes a directory (only if empty).
* `rm -R Folder` : **Recursively** removes directory and all contents.

---

## 🔐 Part 2: Permissions

### Permission Basics
| Symbol | Type | Meaning | Octal Value |
| :---: | :--- | :--- | :---: |
| **r** | Read | View file contents / List directory | **4** |
| **w** | Write | Modify file / Create or delete in directory | **2** |
| **x** | Execute | Run script / Enter directory | **1** |

### Reading the Permission String
Example: `drwxr-xr-x`
1. **Type:** `d` (Directory) or `-` (File)
2. **Owner:** `rwx` (Read, Write, Execute)
3. **Group:** `r-x` (Read, Execute)
4. **Others:** `r-x` (Read, Execute)

### Changing Permissions (`chmod`)

#### 1. Symbolic Mode
Uses characters: `u` (user/owner), `g` (group), `o` (others), `a` (all).
* `chmod u=rwx script.sh` : Owner gets Read, Write, Execute.
* `chmod go=rwx script.sh` : Group and Others get Read, Write, Execute.
* `chmod go-wx script.sh` : **Remove** Write and Execute from Group and Others.
* `chmod g+x script.sh` : **Add** Execute permission to Group.

#### 2. Octal (Number) Mode
Sum the values: Read(4) + Write(2) + Execute(1).
* **7** = `rwx` (4+2+1)
* **6** = `rw-` (4+2)
* **5** = `r-x` (4+1)
* **4** = `r--` (4)

**Examples:**
* `chmod 444 file.sh` : Everyone has Read-only (4,4,4).
* `chmod 744 file.sh` : Owner has Full (7); Group/Others have Read-only (4).
* `chmod 644 file.sh` : Owner has Read+Write (6); Group/Others have Read-only (4).

#### Recursive Permissions
* `chmod -R 777 Test/` : Gives Full permissions to `Test/` and **every file/folder inside it**.
