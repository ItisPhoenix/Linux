Commands to gather details about the operating system, kernel, hardware, and user context.

## 👤 Hostname & User Information

```bash
# Change Hostname
# Opens the hostname file in vim. You must save and reboot (or use hostnamectl) for changes to take effect.
sudo vim /etc/hostname 

# User Groups
# Lists the groups that a specific user belongs to.
groups [username]

```

## 🐧 Distribution (OS) Details

These commands help you identify which version of Linux (Ubuntu, Kali, Debian, CentOS, etc.) is running.

```bash
# Print distribution-specific information (Release, Codename, Description)
lsb_release -a

# View the OS release file (Contains detailed build info)
cat /etc/os-release

```

## ⚙️ CPU & Kernel Information

### CPU Architecture

```bash
# Display detailed information about the CPU architecture
lscpu

```

### Kernel Details (`uname`)

The `uname` command provides information about the Linux kernel and system architecture.

| Command | Description |
| --- | --- |
| `uname -a` | **All**. Prints all available system information. |
| `uname -r` | **Release**. Prints the kernel release version. |
| `uname -p` | **Processor**. Prints the processor type (instruction set). |
| `uname -i` | **Hardware Platform**. Prints the hardware platform details. |
| `uname -o` | **Operating System**. Prints the operating system name (e.g., GNU/Linux). |
