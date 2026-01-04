# Grep, Piping & Redirection

## 🔍 Grep (Global Regular Expression Print)

The `grep` command is used to search for specific text or patterns within files or command output.

```bash
# Basic Search (Case Sensitive)
# Searches for the exact word "dynamic" inside /etc/proxychains.conf
grep "dynamic" /etc/proxychains.conf

# Case Insensitive Search (-i)
# Searches for "dynamic", "DYNAMIC", "Dynamic", etc.
grep -i "dynamic" /etc/proxychains.conf

```

---

## ⛓️ Piping (`|`)

The pipe symbol `|` allows you to take the **output** of the command on the left and use it as the **input** for the command on the right.

```bash
# Method 1: Piping cat into grep
# Displays the file content using 'cat', then filters for "dynamic"
cat /etc/proxychains.conf | grep "dynamic"

# Method 2: Filtering System Command Output
# Runs 'ifconfig' (network config) and filters only the lines containing "inet"
ifconfig | grep inet

```

---

## ➡️ Redirection (`>`)

The greater-than symbol `>` is used to redirect the output of a command into a file.

> **Note:** Using `>` will overwrite the file if it already exists.

```bash
# Example: Save the filtered network info to a file named 'my_ip.txt'
ifconfig | grep inet > my_ip.txt
