The `find` command searches for files and directories within a directory hierarchy. Unlike `locate` (which uses a database), `find` searches the live system, making it more accurate but sometimes slower.

> **Note:** When searching the entire system (root `/`), you usually need to use `sudo` to avoid "Permission denied" errors.

## 🏗 Basic Syntax

```bash
find [path] [options] [expression]

```

### File Types (`-type`)

You can filter results by the type of object:

* `f` : File
* `d` : Directory

---

## 🔍 Searching by Name

### Case Sensitive (`-name`)

This is the standard search. It must match the capitalization exactly.

```bash
# Search the entire system (/) for a file named "proxychains.conf"
sudo find / -type f -name "proxychains.conf"

# Search using wildcards (e.g., all .conf files in /etc)
sudo find /etc -type f -name "*.conf"

```

### Case Insensitive (`-iname`)

Use `-iname` if you don't know the capitalization of the file.

```bash
# Finds "Proxychains.conf", "proxychains.CONF", etc.
sudo find / -type f -iname "proxychains.conf"

```

---

## ⚖️ Searching by Size

You can filter files based on their size using the `-size` flag.

* `+` : Greater than
* `-` : Less than
* `M` : Megabytes
* `k` : Kilobytes
* `G` : Gigabytes

```bash
# Find files named "proxychains.conf" in /etc that are larger than 1MB
# (Note: You can skip '-type' if you only care about name and size)
sudo find /etc -name "proxychains.conf" -size +1M


```
