# File & Directory Ownership

> ⚠️ **Important:** To change file or directory ownership, you must be the **root** user or use `sudo`.

## Change Owner (`chown`)

The `chown` command is used to change the user owner of a file or directory.

```bash
# Syntax: chown [new_owner] [filename]

# Change the owner of 'test.sh' to the user 'root'
sudo chown root test.sh

```

## Change Group (`chgrp`)

The `chgrp` command is used to specifically change the group ownership of a file.

```bash
# Syntax: chgrp [new_group] [filename]

# Change the group ownership of 'test.sh' to the group 'root'
sudo chgrp root test.sh
