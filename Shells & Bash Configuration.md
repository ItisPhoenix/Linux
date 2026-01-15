Manage and configure the shell environment (the command-line interface).

## 🐚 Viewing Available Shells

To see the list of valid login shells installed on your system:

```bash
cat /etc/shells

```

## 🔄 Switching Shells (Temporary)

You can switch to a different shell in your current terminal session simply by typing its name. Type `exit` to return to the previous shell.

* `sh` : Switch to the **Bourne Shell**.
* `dash` : Switch to the **Dash Shell** (Debian Almquist Shell).
* `bash` : Switch to the **Bash Shell** (Bourne Again Shell).
* `zsh` : Switch to the **Z Shell**.

## 🕵️‍♂️ Checking Your Default Shell

To see which shell is assigned to your user by default (executes when you log in), check the `/etc/passwd` file.

```bash
# Syntax: grep [username] /etc/passwd
# Example (if your username is 'kali'):

cat /etc/passwd | grep kali

```

* **Output example:** `kali:x:1000:1000:,,,:/home/kali:/usr/bin/zsh`
* The path at the very end (`/usr/bin/zsh`) is your default shell.

## 🛠 Changing Login Shell (Permanent)

To permanently change the default shell for your user, use the `chsh` (Change Shell) command.

```bash
# Interactive mode (will ask for password and path)
chsh

# One-line command to set Bash as default
chsh -s /bin/bash

# One-line command to set Zsh as default
chsh -s /bin/zsh

```

> **Note:** You must log out and log back in for `chsh` changes to take effect.
