# File Management & Manipulation Commands

A quick reference guide for essential Linux/Unix file management commands.

## 📂 Navigation & Listings

| Command | Description |
| :--- | :--- |
| `pwd` | **P**resent **W**orking **D**irectory. Shows the path of the directory you are currently in. |
| `cd ..` | Step back to the parent (previous) directory. |
| `cd /etc` | Change directory to the absolute path `/etc`. |
| `cd ~` | Change directory to the current user's **home** directory. |

### The `ls` Command (List)

* `ls`
    * Lists files and folders in the current directory (simple format).
* `ls -l`
    * Lists files and folders in **list** format (shows permissions, owner, size, modification date).
* `ls -a`
    * Lists **all** files and folders, including hidden ones (files starting with `.`).
* `ls -al`
    * Combination of list format and all files (hidden included).
* `ls -lh`
    * List format with **human-readable** file sizes (e.g., KB, MB, GB instead of bytes).
* `ls -lR Desktop/`
    * **Recursive** list. Lists files in `Desktop/`, plus all files inside sub-directories within `Desktop/`.

---

## 📝 Creating & Viewing Files

### Creation
* `touch test.txt`
    * Creates an empty file named `test.txt`.
* `mkdir Test`
    * **M**a**k**e **Dir**ectory. Creates a new folder named `Test`.

### Display & Redirection
* `echo "Something"`
    * Prints "Something" to the terminal output.
* `echo "Hello" > test.txt`
    * Redirects the output "Hello" **into** the file `test.txt` (overwrites content).
* `whatis [command]`
    * Displays a one-line description of what a specific command does.

### Reading Content (`cat`)
* `cat [file]`
    * Displays the full content of a file in the terminal.
* `cat /etc/passwd > passwd.txt`
    * Reads the content of `/etc/passwd` and redirects (saves) it into `passwd.txt`.

### Editors
* `nano`
    * A simple, beginner-friendly terminal text editor.
* `vim`
    * A powerful, complex text editor with modal editing.

---

## ✂️ Manipulation (Copy, Move, Remove)

### Copying (`cp`)
* `cp passwd.txt Test`
    * Copies the file `passwd.txt` into the `Test` directory.

### Moving & Renaming (`mv`)
The `mv` command is used for both moving files and renaming them.

1.  **Move:** `mv passwd.txt Test/`
    * Moves `passwd.txt` inside the `Test` folder.
2.  **Rename:** `mv passwd.txt test.txt`
    * Renames the file `passwd.txt` to `test.txt`.

### Removing (`rm`)

> ⚠️ **Warning:** Deleted files are generally not recoverable in the command line.

* `rm [file]`
    * Removes (deletes) a specific file.
* `rmdir [directory]`
    * Removes a directory **only if it is empty**.
* `rm -R [directory]`
    * **Recursive** remove. Deletes a directory and all the files/folders inside it (use with caution).
