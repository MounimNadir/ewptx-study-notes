# Linux Revision Notes

> Practical Linux commands and concepts for system usage, services, networking, permissions, and basic hosting.

---

## 1. Managing Services (Apache Example)

Start the Apache service:

```bash
sudo systemctl start apache2
```

Check its status:

```bash
sudo systemctl status apache2
```

Apache serves files from the default web root:

```bash
cd /var/www/html/
```

Create a test file:

```bash
touch test.txt
echo "hello" > test.txt
```

You can also edit it using `vim`, `nano`, or `vi`.

Verify in the browser:

```
http://127.0.0.1/test.txt
```

You should see **hello** displayed in the page body.

---

## 2. Hosting a Directory with Python HTTP Server

Navigate to the directory you want to host:

```bash
cd ~/Documents/htb/block
```

Start a simple HTTP server (Python 2):

```bash
python2 -m SimpleHTTPServer 8050
```

This creates an HTTP service on port **8050** that serves the current directory.

Create and edit a file:

```bash
touch test1.txt
vim test1.txt
```

### Basic Vim Commands

* `i` → insert mode
* `Esc` → exit insert mode
* `:w` → write (save)
* `:q` → quit
* `:wq` → save and quit

---

## 3. File Search and Command Pipelining

Update the file database (required before using `locate`):

```bash
sudo updatedb
```

Find a file (example: `autorecon`):

```bash
locate autorecon
```

### Pipe (`|`)

The pipe operator sends the output of one command to another:

```bash
command1 | command2
```

Used to filter, manipulate, or analyze command output.

---

## 4. File Permissions and Metadata

Linux permissions:

* **r** → read
* **w** → write
* **x** → execute

Check permissions and metadata:

```bash
ls -l
```

Understanding file metadata (owner, group, permissions, size, timestamps) is essential for system administration and security.

### /tmp Directory

* Temporary directory
* World-writable (`777`)
* Cleared after reboot
* Accessible by all users

---

## 5. Package Management (Debian/Ubuntu)

Update package lists:

```bash
sudo apt update
```

Upgrade installed packages:

```bash
sudo apt upgrade
```

---

## 6. Git Basics

Clone a GitHub repository:

```bash
git clone <repository_url>
```

---

## 7. Networking Commands

Show IP addresses (brief format):

```bash
ip -br a
```

View routing table and default gateways:

```bash
route -n
```

Legacy tools:

```bash
ifconfig
netstat
```

Modern alternative to `netstat`:

```bash
ss
```

---

## 8. Systemd Service Management

Check service status:

```bash
systemctl status <service_name>
```

Start / stop a service:

```bash
systemctl start <service_name>
systemctl stop <service_name>
```

Enable a service at boot:

```bash
sudo systemctl enable postgresql
```

Example:

```bash
systemctl status postgresql
```

---

## 9. User and Group Management Files

Important system files:

* `/etc/passwd` → user account information
* `/etc/shadow` → encrypted passwords (root only)
* `/etc/group` → group definitions

These files are critical for authentication and authorization.

---

## 10. Notes

* Always understand permissions before executing or exposing files
* Prefer modern tools (`ip`, `ss`) over deprecated ones when possible
* Practice reading command output carefully—Linux is transparent by design

---

**File:** `linux_revision.md`

