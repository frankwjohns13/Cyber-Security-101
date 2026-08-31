# TryHackMe Cyber Security 101 Notes

## Introduction
Welcome to my notes for the TryHackMe Cyber Security 101 learning path. \
You can view my TryHackMe Badges here -> [Badges](https://tryhackme.com/p/WickedWizard?tab=badges)

---

<details>
<summary><strong>Module 1 - Finished</strong></summary>

---

<details>
<summary><strong>Room 1 - Offensive Security Intro</strong></summary>

### Room 1 - Offensive Security Intro
Hack your first website (legally in a safe environment) and experience an ethical hacker's job.

**What is Offensive Security?** 
"It involves breaking into computer systems, exploiting software bugs, and finding loopholes in applications to gain unauthorized access." - TryHackMe

**Tool Used**
- **Gobuster** - Takes a list of potential page or directory names and tries accessing a website with each of them.
  - -u → specify the target website
  - -w → specify the wordlist

**End of Room 1**

</details>

---

<details>
<summary><strong>Room 2 - Defensive Security Intro</strong></summary>
  
### Room 2 - Defensive Security Intro
**Goal:** Protect FakeBank from an ongoing attack.

**What is Defensive Security?**\
“Defensive security is the process of defending and securing devices and systems.”

**What does a defender do?**
- Detect and investigate attacks
- Respond before damage occurs

**Practical steps in the room:**
1. Detect Suspicious Activity → Use the Event Management tool to find a suspicious IP address
2. Identify the Attack → Use the Security Analyst Dashboard to see what page the attacker is trying to access
3. Stop the Attack → Create a firewall rule to block the attacker’s IP address

**End of Room 2**

</details>

---

<details>
<summary><strong>Room 3 - Search Skills</strong></summary>

### Room 3 - Search Skills

**Learning Objectives**
- Understand why effective search skills are important in cybersecurity
- Learn how to use specialized search engines and tools
- Identify key resources for researching vulnerabilities

---

#### Why Search Skills Matter

Being able to quickly find accurate technical information is a critical skill for both offensive and defensive security work.

---

#### Shodan  

**Shodan** is a search engine that finds internet-connected devices and systems.

| **Filter** | **Description** | **Example** |
|------------|---------------------------------------------------------------------------------------------|-------------------------|
| `country`  | Restrict results to a specific country code.                                                | `country:IE`            |
| `port`     | Filter by a specific port number or a range                                                 | `port:22`               |
| `org`      | Scope results in a named organization or ASN Identifier (Who owns a range of IP addresses). | `AS7224 (AWS)`          |
| `hostname` | Match against a specific hostname or domain.                                                | `hostname:fakebank.thm` |

---

#### VirusTotal

**VirusTotal** nalyzes files and URLs using many antivirus engines and security tools in one place. 
It helps determine whether a file or website is malicious. 

---

#### Vulnerability Databases (CVE)

**Common Vulnerabilities and Exposures (CVE)** is the closest thing to a universal dictionary of know vulnerabilities. 

**CVE (Common Vulnerabilities and Exposures)** is a standardized list of publicly known security vulnerabilities.
- Format: `CVE-YEAR-NUMBER` (example: `CVE-2021-44228`)
- Each vulnerability is scored based on:
  - **Impact** — How much damage it can cause
  - **Complexity** — How difficult it is to exploit
  - **Availability** — How widespread or accessible it is

---

**End of Room 3**
  
</details>

---

**End Module 1**

</details> <!-- End of Module 1 --> 

---














<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 1
***********************************************************************
***********************************************************************
-->














<details>
<summary><strong>Module 2 - Finished</strong></summary>

---

<details>
<summary><strong>Room 1 - Linux Fundamentals Part 1</strong></summary>

---

**Learning Objectives**
- Understand where Linux is commonly used
- Learn essential Linux commands for navigating the system
- Practice basic file and text operations

---

### Room 1 - Linux Fundamentals Part 1 

#### Where is Linux Used?

Linux powers many systems, including:
- Websites and web servers
- Car entertainment and control systems
- Critical infrastructure (traffic lights, industrial sensors)
- Phones and tablets
- Point-of-sale devices

---

#### Essential Linux Commands

| Command | Purpose | Example |
|---------|---------|---------|
| `whoami` | Shows the current username | `whoami` |
| `echo` | Displays text on the screen | `echo "Hello"` |
| `pwd` | Prints the current working directory | `pwd` |
| `ls` | Lists files and folders | `ls` |
| `cd` | Changes directory | `cd Documents` |
| `cat` | Displays the contents of a file | `cat notes.txt` |
| `find` | Searches for files by name | `find -name passwords.txt` |
| `grep` | Searches for text inside files | `grep "password" file.txt` |

---

#### Useful Operators

| Operator | Purpose | Example |
|----------|---------|---------|
| `&` | Runs a command in the background | `long_command &` |
| `&&` | Runs the next command only if the previous one succeeds | `mkdir test && cd test` |
| `>` | Redirects output (overwrites the file) | `ls > files.txt` |
| `>>` | Redirects output (appends to the file) | `ls >> files.txt` |

---

**End of Room 1**


  
</details> <!-- End Room 1  -->

---

<details>
<summary><strong>Room 2 - Linux Fundamentals Part 2</strong></summary>

---

### Room 2 - Linux Fundamentals Part 2

**Learning Objectives**
- Understand flags and arguments
- Work with the advanced filesystem
- Use copy and move commands
- Manage file and folder permissions

---

#### What is SSH?

**SSH (Secure Shell)** is a protocol used to securely connect to remote devices.
- Allows you to run commands on another machine
- Encrypts all data sent over the network

**Basic syntax:**
```
bash
ssh username@ip_address
```

**Example:**
```
bash
ssh frank@192.168.1.13
```

---

#### Flags and Help

Most Linux commands accept flags (also called switches) that change their behavior.

| **Command** | **Purpose**                |
|-------------|----------------------------|
| ls --help   | Quick help for the command |
| man ls      | Full manual page           |

**Example:**
```
bash
ls -a  # Lists all files, including hidden ones
```

---

#### Common File Management Commands

| **Command** | **Full Name**  | **Purpose**              | **Example**           |
|-------------|----------------|--------------------------|-----------------------|
| touch       | touch          | Create an empty file     | touch test.txt        |
| mkdir       | make directory | Create a folder          | mkdir folder1         |
| cp          | copy           | Copy a file or folder    | cp test.txt folder1/  |
| mv          | move           | Move a file or folder    | mv test.txt test2.txt |
| rm          | remove         | Remove a file or folder  | rm test.txt           |
| file        | file           | Shows the type of a file | file test.txt         |

---

#### File Permissions

Linux permissions control who can read, write, or execute a file.

**Permission types:**
- `r` = Read
- `w` = Write
- `x` = Execute

**Numeric values:**

| **Permission** | **Value** |
|----------------|:---------:|
| Read (`r`)     | 4         |
| Write (`w`)    | 2         |
| Execute (`x`)  | 1         |

**Permissions order:**

| **Section** | **Applies To** |
|-------------|----------------|
| First 3 characters | Owner   |
| Next 3 characters  | Group   |
| Last 3 characters  | Others  |

**Examples:**

| **Symbolic** | **Numeric** | **Meaning**                                      |
|--------------|:-----------:|--------------------------------------------------|
| `rwxr-xr-x`  | 755         | Owner: full access, Group/Others: read + execute |
| `rw-r--r--`  | 644         | Owner: read/write, Group/Others: read only       |
| `rwx------`  | 700         | Only the owner has access                        |

---

#### Important Linux Directories

| **Directory** | **Purpose**                                |
|---------------|--------------------------------------------|
|`/etc`         | System configuration files                 |
| `/var`        | Variable data (logs, caches, etc.)         |
| `/root`       | Home directory of the root user            |
| `/tmp`        | Temporary files (often cleared on reboot ) |

---

**End of Room 2**


</details> <!-- End Room 2 -->

---

<details>
<summary><strong>Room 3 - Linux Fundamentals Part 3</strong></summary>

---

### Room 3 - Linux Fundamentals Part 3

**Learning Objectives**
- Use terminal text editors
- Download and transfer files
- Manage processes
- Schedule tasks with cron
- Understand basic package management and logs

---

#### Terminal Text Editors

**Nano** (beginner-friendly)
```bash
nano filename
```

**Useful features:**
- Search text
- Copy and paste
- Jump to a line number

Exit **Nano**: `Ctrl + X` (it will ask if you want to save)

**Vim** (more powerful, steeper learning curve)
- Highly customizable
- Syntax highlighting
- Available on almost every Linux system

---

#### Downloading and Transferring Files

Download files with `wget`

```bash
wget https://example.com/file.pdf
```

**Transfer files with scp (Secure Copy)**

Copy from your computer → remote machine:

```bash
scp thisfile.txt ubuntu@192.168.10.13:/home/ubuntu/thisfile.txt
```

Copy from remote machine → your computer:

```bash
scp ubuntu@192.168.10.13:/home/ubuntu/thisfile.txt thisfile.txt
```

---

#### Processes

**View running processes**

```bash
ps       # Processes for the current user
ps aux   # Processes for all users
```

**Kill a process**

```bash
kill 1013
```

**Common signals:**

| **Signal** | **Meaning** |
|------------|-------------|
| SIGTERM    | Graceful stop (allows cleanup) |
| SIGKILL    | Force kill (no cleanup) |
| SIGSTOP    | Pause/suspend the process |

Manage services with `systemctl`

```bash
systemctl start apache2
systemctl stop apache2
systemctl enable apache2
systemctl disable apache2
systemctl status apache2
```

**Background and Foreground**

```bash
cp largefile.txt /folder/ &     # Run in background
Ctrl + Z                        # Suspend current process
fg                              # Bring process back to foreground
```

---

#### Scheduling Tasks with Cron

Crontab format:

```text
MIN HOUR DOM MON DOW COMMAND
```

| **Field** | **Meaning**         |
|-----------|---------------------|
| MIN       | Minute (0–59)       |
| HOUR      | Hour (0–23)         |
| DOM       | Day of month (1–31) |
| MON       | Month (1–12)        |
| DOW       | Day of week (0–7)   |
| CMD       | Command to run      |

**Example: Backup Documents every 12 hours**
```bash
0 */12 * * * cp -R /home/user/Documents /var/backups/
```

**Edit your crontab:**

```bash
crontab -e
```

Helpful sites:
- [crontab guru](https://crontab.guru/)
- [crontab generator](https://crontab-generator.org/)

---

#### Package Management

Add a repository:

```bash
add-apt-repository <repository>
```

**Remove a repository:**

```bash
add-apt-repository --remove <repository>
```

---

#### System Logs

Important logs are usually found in:

```text
/var/log/
```

Two common types:
- **Access logs** — Who accessed what
- **Error logs** — What went wrong

---

**End of Room 3**

  
</details> <!-- End Room 3 -->

---


**End of Module 2**
  
</details> <!-- End of Module 2 --> 

---













<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 2
***********************************************************************
***********************************************************************
-->















<details>
<summary><strong>Module 3 - Currently in Progress</strong></summary>

---

<details>
<summary><strong>Room 1 - Windows Fundamentals 1</strong></summary>
  
---

### Room 1 - Windows Fundamentals 1

**Learning Objectives**
- Understand the basic history and current versions of Windows
- Identify the main components of the Windows Desktop (GUI)
- Explain the NTFS file system and basic permissions
- Understand user accounts, profiles, and User Account Control (UAC)
- Navigate Settings, Control Panel, and Task Manager

---

#### Brief History of Windows

Windows has been the dominant desktop operating system for decades.

Key versions:
- **Windows XP** — Long-lasting and widely used
- **Windows Vista** — Poorly received and short-lived
- **Windows 7** — Popular replacement for XP
- **Windows 8/8.1** — Short-lived
- **Windows 10** — Widely adopted
- **Windows 11** — Current desktop version (Home and Pro)
- **Windows Server 2025** — Current server version

The lab VM uses **Windows Server 2019 Standard**.

---

#### The Windows Desktop (GUI)

Main components of the Desktop:

| Component | Purpose |
|-----------|---------|
| **Desktop** | Area for shortcuts, files, and folders |
| **Start Menu** | Access to apps, settings, and power options |
| **Search Box** | Search for apps, files, and settings |
| **Task View** | Switch between open windows and virtual desktops |
| **Taskbar** | Shows open apps and pinned shortcuts |
| **Notification Area** | Clock, volume, network, and system icons |

**Useful tip:** Right-click almost any item to see more options.

---

#### The File System – NTFS

Modern Windows systems use **NTFS** (New Technology File System).

**Advantages of NTFS:**
- Supports large files (over 4GB)
- Folder and file permissions
- Compression
- Encryption (EFS)
- Journaling (can recover from failures)

**Common NTFS Permissions:**
- Full control
- Modify
- Read & Execute
- List folder contents
- Read
- Write

**Alternate Data Streams (ADS)**  
NTFS allows files to contain more than one stream of data.  
This feature has been used by malware to hide data, but it also has legitimate uses.

---

#### Important Folders

| Folder | Purpose |
|--------|---------|
| `C:\Windows` | Main Windows operating system folder |
| `C:\Windows\System32` | Critical system files and tools |
| `C:\Users` | User profile folders |

**Warning:** Be very careful with the `System32` folder. Deleting files here can break the operating system.

---

#### User Accounts and Permissions

Two main local account types:

| Account Type | Privileges |
|--------------|------------|
| **Administrator** | Can make system-wide changes |
| **Standard User** | Limited to their own files and settings |

User profiles are stored in:
`C:\Users<username>`

Common profile folders:
- Desktop
- Documents
- Downloads
- Pictures
- Music

You can manage users and groups with:
`lusrmgr.msc`

---

#### User Account Control (UAC)

**UAC** helps protect the system by prompting for permission when a task needs elevated privileges.

- Standard users will see a password prompt
- Administrators will usually see a Yes/No prompt
- The built-in Administrator account is not affected by UAC by default

This reduces the chance of malware making system changes without the user noticing.

---

#### Settings and Control Panel

| Tool | Purpose |
|------|---------|
| **Settings** | Modern, simpler interface for common changes |
| **Control Panel** | Older interface for more advanced system settings |

Both can be accessed from the Start Menu.  
Some options in Settings will open Control Panel windows.

---

#### Task Manager

**Task Manager** shows:
- Running applications and processes
- CPU and memory usage
- Performance information

**Open it by:**
- Right-clicking the taskbar → Task Manager  
- Or pressing `Ctrl + Shift + Esc`

---
**End of Room 1**



</details> <!-- End of Room 1 -->

---

<details>
<summary><strong>Room 2 - Windows Fundamentals 2</strong></summary>
  
---

### Room 2 - Windows Fundamentals 2

**Learning Objectives**
- Use System Configuration (MSConfig) and Advanced System Settings
- Manage User Account Control (UAC) settings
- Navigate Computer Management tools
- Use System Information and Resource Monitor
- Run basic Command Prompt commands
- Understand the purpose of the Windows Registry

---

#### System Configuration (MSConfig)

**MSConfig** is used for advanced troubleshooting, especially startup issues.

**Open it:** Start Menu → search `msconfig`  
(Requires Administrator rights)

**Tabs:**

| Tab | Purpose |
|-----|---------|
| **General** | Choose Normal, Diagnostic, or Selective startup |
| **Boot** | Configure boot options |
| **Services** | View and manage system services |
| **Startup** | Startup items (managed better in Task Manager on client OS) |
| **Tools** | Launch useful system utilities |

**Note:** On Windows Server, startup programs are best viewed via:
`shell:startup`

---

#### Advanced System Settings

Search for **View advanced system settings**.

Useful options:
- **Performance Settings** → Configure virtual memory (page file)
- **Startup and Recovery** → Configure crash dump settings

**Common crash dump types:**
- Automatic memory dump
- Kernel memory dump
- Small memory dump
- Complete memory dump

---

#### User Account Control (UAC) Settings

UAC controls how Windows notifies you when apps try to make system changes.

**Four levels:**

| Level | Behavior |
|-------|----------|
| Always notify | Highest security (screen dims) |
| Notify for apps only | Default setting |
| Notify without dimming | Same as above, no dimming |
| Never notify | UAC turned off (not recommended) |

---

#### Computer Management

Open with: `compmgmt.msc`

**Main sections:**

**System Tools**
- **Task Scheduler** — Schedule programs/scripts to run automatically
- **Event Viewer** — View system, security, and application logs
- **Shared Folders** — View shares, sessions, and open files
- **Local Users and Groups** — Manage users and groups (`lusrmgr.msc`)
- **Performance Monitor** — Analyze system performance
- **Device Manager** — View and manage hardware

**Storage**
- **Disk Management** — Create, shrink, extend partitions and assign drive letters

**Services and Applications**
- View and manage Windows services
- Configure **WMI** (Windows Management Instrumentation)

**Service Startup Types:**
- Automatic
- Manual
- Disabled

---

#### System Information (`msinfo32`)

Provides a detailed overview of the system.

**Sections:**
- **System Summary** — General hardware and OS info
- **Hardware Resources**
- **Components** — Installed devices
- **Software Environment** — Drivers, environment variables, network connections, etc.

Useful for troubleshooting and gathering system details.

---

#### Resource Monitor (`resmon`)

Shows real-time usage of:

- CPU
- Memory
- Disk
- Network

Useful for finding which process is using resources or locking files.

---

#### Command Prompt Basics

| Command | Purpose |
|---------|---------|
| `hostname` | Show computer name |
| `whoami` | Show current user |
| `ipconfig` | Show network configuration |
| `ipconfig /?` | Help for a command |
| `netstat` | Show network connections |
| `net user` | Manage user accounts |
| `cls` | Clear the screen |

**Useful net commands:**
```bash
net user
net localgroup
net share
net session
```

**Registry Editor**
(`regedit`)

The Windows Registry is a hierarchical database that stores system and application configuration settings.

It contains information about:
- User profiles
- Installed applications
- Hardware
- System settings

Warning: Making incorrect changes to the registry can break the system. Only advanced users should edit it.

---

**End of Room 2**

</details> <!-- End of Room 2 -->

---

<details>
<summary><strong>Room 3 - Windows Fundamentals 3</strong></summary>
  
---

### Room 3 - Windows Fundamentals 3

**Learning Objectives**
- Understand Windows Update and Patch Tuesday
- Navigate Windows Security features
- Explain Virus & threat protection settings
- Understand Firewall profiles and SmartScreen
- Describe BitLocker and Volume Shadow Copy Service (VSS)

---

#### Windows Update

Windows Update delivers:
- Security patches
- Feature updates
- Microsoft product updates (including Defender)

**Patch Tuesday**  
Most updates are released on the **second Tuesday of each month**.  
Critical updates can be released outside this schedule.

Updates can be postponed, but they eventually install and may require a restart.

---

#### Windows Security

**Windows Security** is the central place to manage device protection.

**Main protection areas:**
- Virus & threat protection
- Firewall & network protection
- App & browser control
- Device security

**Status icons:**
- 🟢 Green → Protected
- 🟡 Yellow → Recommendation available
- 🔴 Red → Immediate attention needed

---

#### Virus & Threat Protection

**Scan options:**
- **Quick scan** — Checks common threat locations
- **Full scan** — Scans the entire system
- **Custom scan** — Scan selected files/folders

**Key settings:**
- **Real-time protection** — Blocks malware as it tries to run
- **Cloud-delivered protection** — Uses latest threat data from the cloud
- **Automatic sample submission** — Sends samples to Microsoft
- **Controlled folder access** — Protects important folders from unauthorized changes
- **Exclusions** — Files/folders skipped by scans (use carefully)

**Threat history includes:**
- Last scan results
- Quarantined threats
- Allowed threats

---

#### Firewall & Network Protection

A **firewall** controls what traffic is allowed in and out of the system.

**Three firewall profiles:**

| Profile | Used For |
|---------|----------|
| **Domain** | Corporate domain networks |
| **Private** | Home or trusted networks |
| **Public** | Public Wi-Fi (coffee shops, airports, etc.) |

You can:
- Turn the firewall on/off (not recommended)
- Block all incoming connections
- Allow specific apps through the firewall

**Advanced tool:** `wf.msc`

---

#### App & Browser Control

Uses **Microsoft Defender SmartScreen** to protect against:
- Phishing websites
- Malicious apps
- Dangerous downloads

**Settings options:**
- Warn
- Block
- Off

Also includes **Exploit protection** features built into Windows.

---

#### Device Security

**Core isolation / Memory Integrity**  
Helps prevent attacks from injecting malicious code into high-security processes.

**Trusted Platform Module (TPM)**  
A hardware security chip that supports encryption and secure cryptographic operations.

---

#### BitLocker

**BitLocker** is Windows’ full-disk encryption feature.

It protects data if a device is lost or stolen.  
Best protection is available when used with a **TPM**.

---

#### Volume Shadow Copy Service (VSS)

**VSS** creates point-in-time snapshots (shadow copies) of data.

These snapshots are used for:
- System Restore
- Creating restore points
- Recovering files

**Security note:**  
Some malware (especially ransomware) tries to delete shadow copies to prevent recovery.

---

#### Key Security Takeaway

Windows includes many built-in security tools.  
Keeping them enabled and updated significantly improves protection.

Attackers often abuse legitimate Windows tools (**Living Off The Land**) to avoid detection.

---

**End of Room 3**


</details> <!-- End of Room 3 -->

---

<details>
<summary><strong>Room 4 - Active Directory Basics</strong></summary>
  
---

### Room 4 - Active Directory Basics

**Learning Objectives**
- Coming soon

*Notes coming soon*












































---

**End of Room 4**

</details> <!-- End of Room 4 -->

















---

**End of Module 3**

  
</details> <!-- End of Module 3 --> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 3
***********************************************************************
***********************************************************************
-->

<details>
<summary><strong>Module 4</strong></summary>





























  
</details> <!-- End of Module 4 --> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 4
***********************************************************************
***********************************************************************
-->

<details>
<summary><strong>Module 5</strong></summary>































  
</details> <!-- End of Module 5 --> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 5
***********************************************************************
***********************************************************************
-->

<details>
<summary><strong>Module 6</strong></summary>




























  
</details> <!-- End of Module 6 --> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 6
***********************************************************************
***********************************************************************
-->

<details>
<summary><strong>Module 7</strong></summary>





























  
</details> <!-- End of Module 7 --> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 7
***********************************************************************
***********************************************************************
-->

<details>
<summary><strong>Module 8</strong></summary>































  
</details> <!-- End of Module 8 --> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 8
***********************************************************************
***********************************************************************
-->

<details>
<summary><strong>Module 9</strong></summary>






























  
</details> <!-- End of Module 9--> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 9
***********************************************************************
***********************************************************************
-->

<details>
<summary><strong>Module 10</strong></summary>



























  
</details> <!-- End of Module 10 --> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 10
***********************************************************************
***********************************************************************
-->

<details>
<summary><strong>Module 11</strong></summary>
































  
</details> <!-- End of Module 11 --> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 11
***********************************************************************
***********************************************************************
-->

<details>
<summary><strong>Module 12</strong></summary>





























  
</details> <!-- End of Module 12 --> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 12
***********************************************************************
***********************************************************************
-->

<details>
<summary><strong>Module 13</strong></summary>




























  
</details> <!-- End of Module 13 --> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 13
***********************************************************************
***********************************************************************
-->

<details>
<summary><strong>Module 14</strong></summary>






























  
</details> <!-- End of Module 14 --> 

---

<!--
***********************************************************************
***********************************************************************
                       END OF MODULE 14
***********************************************************************
***********************************************************************
-->




<!-- End of File -->
