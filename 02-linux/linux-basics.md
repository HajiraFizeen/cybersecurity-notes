# 🐧 Linux Basics for Cybersecurity

## 1. What is Linux?

Linux is an open-source operating system widely used in servers, cloud environments, cybersecurity, and penetration testing.

**Why Linux matters in cybersecurity:**
- Managing files and directories
- Analyzing logs
- Managing users and permissions
- Running security tools
- Automating tasks with Bash scripts

## 2. Basic Linux Commands

### Check the current directory
```bash
pwd
```

### List files and directories
```bash
ls
ls -la
```
`ls -la` displays hidden files and detailed file information.

### Change directory
```bash
cd /home/kali
cd ..
cd ~
```

### Create a directory
```bash
mkdir security-notes
```

### Create an empty file
```bash
touch notes.txt
```

### Read a text file
```bash
cat notes.txt
less notes.txt
```

### Copy a file
```bash
cp notes.txt notes-backup.txt
```

### Move or rename a file
```bash
mv notes.txt linux-notes.txt
```

### Remove a file
```bash
rm notes.txt
```

**Warning:** `rm` can permanently delete files. Check the path before running it.

## 3. File Permissions

Linux permissions control who can read, modify, or execute files.

Three permission groups:
- **User (u):** file owner
- **Group (g):** associated group
- **Others (o):** everyone else

Permission types:
- `r` — Read
- `w` — Write
- `x` — Execute

Example:
```bash
ls -l
```

Sample output:
```text
-rwxr-xr-- 1 kali kali 100 Oct 22 script.sh
```

This means:
- Owner: read, write, execute
- Group: read, execute
- Others: read only

### Change permissions
```bash
chmod 750 script.sh
```

For `750`:
- Owner: `7` = read + write + execute
- Group: `5` = read + execute
- Others: `0` = no permissions

### Change file ownership
```bash
sudo chown user:group file.txt
```

Use appropriate privileges and verify the intended owner and group before making changes.

## 4. Users and Privileges

### Display the current user
```bash
whoami
```

### Display user and group IDs
```bash
id
```

### List logged-in users
```bash
who
```

### Run a command with elevated privileges
```bash
sudo <COMMAND>
```

`sudo` runs an authorized command with elevated privileges according to system policy.

**Security tip:** Avoid running commands as root unless necessary. Use least privilege.

## 5. Process Management

### Display running processes
```bash
ps aux
```

### Monitor system processes
```bash
top
```

### Find a process by name
```bash
pgrep -a ssh
```

### Stop a process gracefully
```bash
kill <PID>
```

Replace `<PID>` with the actual process ID. Confirm the process before terminating it.

## 6. Networking Commands

### Show IP addresses
```bash
ip addr
```

### Display routes
```bash
ip route
```

### Test connectivity
```bash
ping -c 4 127.0.0.1
```

### Show listening sockets and ports
```bash
ss -tuln
```

### Test DNS resolution
```bash
getent hosts example.com
```

### View network configuration
```bash
ip link
```

These commands help troubleshoot connectivity and inspect network services.

## 7. Searching for Files and Text

### Find a file by name
```bash
find . -name "notes.txt"
```

### Find files owned by a user
```bash
find /home -user kali 2>/dev/null
```

### Search for text in a file
```bash
grep "error" application.log
```

### Search recursively
```bash
grep -Rni "failed" /var/log 2>/dev/null
```

`2>/dev/null` suppresses error messages, such as permission-denied messages. It does not fix the underlying permission issue.

## 8. Logs for Security Analysis

Logs help analysts investigate errors, login attempts, and system activity.

Common locations include:
- `/var/log/auth.log` — authentication events on Debian-based systems, when configured
- `/var/log/syslog` — general system messages on systems using this logging setup
- `/var/log/` — directory containing many system and application logs

### Search for failed login messages
```bash
sudo grep -i "failed" /var/log/auth.log
```

### View recent system journal messages
```bash
journalctl -n 50
```

### View authentication-related journal messages
```bash
sudo journalctl -u ssh
```

Log locations and available services vary by Linux distribution and configuration.

## 9. Package Management on Kali Linux

### Update package information
```bash
sudo apt update
```

### Upgrade installed packages
```bash
sudo apt upgrade
```

### Install a package
```bash
sudo apt install nmap
```

### Search for a package
```bash
apt search wireshark
```

Only install software from trusted sources and review changes before confirming package operations.

## 10. Bash Basics

Bash is a command-line shell that interprets commands and supports scripting.

Example:
```bash
#!/bin/bash
echo "Learning Linux for cybersecurity"
whoami
pwd
```

Save this as `hello.sh`.

Run it with:
```bash
bash hello.sh
```

Bash scripts can automate repetitive tasks, process logs, and support security workflows.

## 11. Useful Cybersecurity Commands

| Command | Purpose |
|---|---|
| `whoami` | Identify current user |
| `id` | Display user and group IDs |
| `uname -a` | Show kernel and system information |
| `df -h` | Check disk space |
| `free -h` | Check memory usage |
| `ps aux` | Inspect processes |
| `ss -tuln` | List listening TCP/UDP sockets |
| `ip addr` | Display network interfaces |
| `journalctl` | Query systemd journal logs |
| `file sample.bin` | Identify a file's type |

## 12. Linux Security Best Practices

- Keep the operating system and packages updated.
- Apply least-privilege permissions.
- Avoid sharing accounts.
- Protect SSH access and disable unnecessary services.
- Review authentication and system logs.
- Do not execute unknown scripts as root.
- Protect secrets, credentials, and private keys.
- Back up important files.

## 13. Practice Checklist

- [ ] Navigate directories using `pwd`, `ls`, and `cd`.
- [ ] Create, copy, rename, and read files.
- [ ] Understand permissions using `ls -l` and `chmod`.
- [ ] Inspect users and processes.
- [ ] Display network interfaces and listening ports.
- [ ] Search a sample log using `grep`.
- [ ] Write and run a simple Bash script.

## Learning Resources

- Linux manual pages: https://man7.org/linux/man-pages/
- GNU Bash manual: https://www.gnu.org/software/bash/manual/
- Kali Linux documentation: https://www.kali.org/docs/

---

**Key takeaway:** Linux fundamentals help cybersecurity professionals investigate systems, understand permissions, troubleshoot networks, and analyze security logs.
