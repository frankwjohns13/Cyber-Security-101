# TryHackMe Cyber Security 101 Notes

## Introduction
Welcome to my notes for the TryHackMe Cyber Security 101 learning path. \
You can view my TryHackMe Badges here -> [Badges](https://tryhackme.com/p/WickedWizard?tab=badges)

---

<details>
<summary><strong>Module 1: Start You Cyber Security Journey - Finished</strong></summary>

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
<summary><strong>Module 2: Linux Foundamentals - Finished</strong></summary>

---

<details>
<summary><strong>Room 1 - Linux Fundamentals Part 1</strong></summary>


---

### Room 1 - Linux Fundamentals Part 1 

**Learning Objectives**
- Understand where Linux is commonly used
- Learn essential Linux commands for navigating the system
- Practice basic file and text operations

---

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
<summary><strong>Module 3: Windows and AD Fundamentals - Finished</strong></summary>

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
- Explain what Active Directory and a Windows Domain are
- Identify key AD objects (users, machines, groups, OUs)
- Manage users and computers in Active Directory
- Understand Group Policy Objects (GPOs)
- Describe Kerberos and NetNTLM authentication
- Explain trees, forests, and trust relationships

---

#### What is a Windows Domain?

A **Windows Domain** is a group of users and computers managed centrally by a business.

**Active Directory (AD)** is the central repository that stores information about the network.  
The server that runs Active Directory is called a **Domain Controller (DC)**.

**Main advantages:**
- Centralized identity management
- Centralized security policy management

---

#### Active Directory Objects

| Object Type | Description |
|-------------|-------------|
| **Users** | People or service accounts that can authenticate and be given permissions |
| **Machines** | Computer accounts (name ends with `$`, e.g., `DC01$`) |
| **Security Groups** | Used to grant permissions to resources |

**Important Default Groups:**

| Group | Purpose |
|-------|---------|
| Domain Admins | Full administrative rights over the domain |
| Server Operators | Can administer Domain Controllers |
| Backup Operators | Can access any file for backup purposes |
| Account Operators | Can create and modify accounts |
| Domain Users | All user accounts in the domain |
| Domain Computers | All computers in the domain |
| Domain Controllers | All Domain Controllers |

---

#### Organizational Units (OUs) vs Security Groups

| Feature | Organizational Units (OUs) | Security Groups |
|---------|---------------------------|-----------------|
| Main purpose | Apply policies | Grant permissions to resources |
| Membership | A user can only be in **one OU** | A user can be in **many groups** |
| Typical use | Department structure (Sales, IT, etc.) | Access to shares, printers, etc. |

---

#### Managing Users in AD

Tool: **Active Directory Users and Computers**

Common tasks:
- Create / delete users
- Reset passwords
- Organize users into OUs

**Delegation**  
You can give limited permissions (e.g., password reset) to specific users over certain OUs without making them Domain Admins.

---

#### Managing Computers in AD

By default, machines join the **Computers** container.  
Best practice is to organize them into OUs such as:

- Workstations
- Servers
- Domain Controllers (already separated by default)

This allows different policies for different types of devices.

---

#### Group Policy Objects (GPOs)

**GPOs** are collections of settings that can be applied to users or computers.

**Key points:**
- Created under **Group Policy Objects**
- Linked to OUs (or the domain)
- Apply to the linked OU and all sub-OUs
- Distributed via the **SYSVOL** share

**Force policy update:**
```powershell
gpupdate /force
```

**Common examples:**
- Restrict Control Panel access
- Auto-lock screen after inactivity
- Password policies

---

#### Authentication Methods

**Kerberos (default modern protocol)
1. User authenticates to the Key Distribution Center (KDC) and receives a TGT
2. User uses the TGT to request a TGS for a specific service
3. User presents the TGS to the service to gain access

**NetNTLM (legacy)**  
Uses a challenge-response mechanism.

The password (or hash) is never sent over the network.

---

#### Trees, Forests, and Trusts

| **Term** | **Meaning**                                                                           |
|----------|---------------------------------------------------------------------------------------|
| Tree     | Multiple domains that share the same namespace (e.g., `uk.thm.local`, `us.thm.local`) |
| Forest   | Collection of multiple trees (different namespaces)                                   |
| Trust    | Allows users from one domain to access resources in another                           |

**Trust types:**
- One-way trust — Access flows in one direction
- Two-way trust — Mutual access (default when domains are joined in a tree/forest)

Having a trust does not automatically grant access — permissions must still be assigned.


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
<summary><strong>Module 4: Command Line - Finished</strong></summary>

---

<details> <!-- Starts Room 1-->
<summary><strong>Room 1 - Windows Command Line</strong></summary>

---

### Room 1 - Windows Command Line

**Learning Objectives**
- Display basic system information
- Check and troubleshoot network configuration
- Manage files and folders
- View and manage running processes

---

#### Why Use the Command Line?

Advantages of the CLI:
- Faster and more efficient once learned
- Lower resource usage
- Easier automation with scripts
- Better for remote management (especially over SSH)

---

#### Basic System Information

| Command | Purpose |
|---------|---------|
| `ver` | Show Windows version |
| `systeminfo` | Detailed system information (OS, hardware, memory, etc.) |
| `set` | Display environment variables (including the system `Path`) |
| `cls` | Clear the screen |
| `help` | Show help for a command |

**Tip:** Pipe long output through `more` to view it page by page:  
```cmd
driverquery | more
```

---

#### Network Troubleshooting

| **Command**         | **Purpose**                                                    |
|---------------------|----------------------------------------------------------------|
| `ipconfig`          | Show basic network configuration                               |
| `ipconfig /all`     | Show detailed network configuration (DNS, DHCP, MAC, etc.)     |
| `ping <target>`	    | Test connectivity to a host                                    |
| `tracert <target>`  | Trace the route to a host                                      |
| `nslookup <domain>` | Look up IP address of a domain                                 |
| `netstat`           | Show current network connections                               |
| `netstat -abon`	    | Show all connections, listening ports, process names, and PIDs |


**Useful netstat options:**
- `-a` → All connections and listening ports
- `-b` → Show the executable name
- `-o` → Show Process ID (PID)
- `-n` → Show numerical addresses and ports

---

#### File and Directory Management

**Directory commands:**  
| **Command**    | **Purpose**                                |
|----------------|--------------------------------------------|
| `cd`           | Show current directory or change directory |
| `cd ..`	       | Go up one level                            |
| `dir`	         | List files and folders                     |
| `dir /a`       | Include hidden and system files            |
| `dir /s`       | Include subdirectories                     |
| `tree`         | Show directory structure visually          |
| `mkdir <name>` | Create a directory                         |
| `rmdir <name>` | Remove an empty directory                  |

**File commands:**  
| **Command**                    | **Purpose**                        |
|--------------------------------|------------------------------------|
| `type <file>`                  | Display contents of a text file    |
| `more <file>`                  | View a long text file page by page |
| `copy <source> <destination>`  | Copy a file                        |
| `move <source> <destination>`  | Move or rename a file              |
| `del <file>` or `erase <file>` | Delete a file                      |

**Wildcard:**  
**Use `*` to match multiple files (e.g., `copy *.txt C:\backup`)**

---

#### Process Management

| **Command**                            | **Purpose**                |
|----------------------------------------|----------------------------|
| `tasklist`                             | List running processes     |
| `tasklist /FI "imagename eq sshd.exe"` |Filter processes by name    |
| `taskkill /PID <number>`               | Terminate a process by PID |

---

#### Extra Useful Commands

| **Command**    | **Purpse**                   |
|----------------|------------------------------|
| `chkdsk`       | Check disk for errors        |
| `driverquery`  | List installed drivers       |
| `sfc /scannow` | Scan and repair system files |


</details> <!-- Ends Room 1-->

---

<details> <!-- Starts Room 2-->
<summary><strong>Room 2 - Windows PowerShell</strong></summary>

---

### Room 2 - Windows PowerShell

**Learning Objectives**
- Understand what PowerShell is and why it is powerful
- Learn the basic Verb-Noun cmdlet structure
- Navigate the file system and work with files
- Use piping, filtering, and sorting
- Gather system and network information
- Perform basic real-time system analysis

---

#### What is PowerShell?

PowerShell is a **command-line shell**, **scripting language**, and **configuration management framework** built on the .NET framework.

**Key difference from Command Prompt:**  
PowerShell works with **objects** (data + properties + methods) instead of plain text. This makes it much more powerful for automation and data manipulation.

---

#### Basic Syntax: Verb-Noun

PowerShell commands are called **cmdlets** and follow a consistent naming pattern:

| Verb | Noun | Example |
|------|------|---------|
| Get | Content | `Get-Content` |
| Set | Location | `Set-Location` |
| New | Item | `New-Item` |
| Remove | Item | `Remove-Item` |

**Essential discovery cmdlets:**

| Cmdlet | Purpose |
|--------|---------|
| `Get-Command` | List available commands |
| `Get-Help <cmdlet>` | Show help for a command |
| `Get-Alias` | List command aliases |
| `Get-Help <cmdlet> -Examples` | Show usage examples |

**Common aliases:**
- `dir` / `ls` → `Get-ChildItem`
- `cd` → `Set-Location`
- `cat` / `type` → `Get-Content`
- `clear` → `Clear-Host`

---

#### Navigating the File System

| Cmdlet | Purpose | Traditional Equivalent |
|--------|---------|------------------------|
| `Get-ChildItem` | List files and folders | `dir` / `ls` |
| `Set-Location` | Change directory | `cd` |
| `New-Item` | Create file or folder | `mkdir` / `echo` |
| `Remove-Item` | Delete file or folder | `del` / `rmdir` |
| `Copy-Item` | Copy file or folder | `copy` |
| `Move-Item` | Move or rename | `move` |
| `Get-Content` | Read file contents | `type` / `cat` |

**Examples:**
```powershell
Get-ChildItem
Set-Location -Path ".\Documents"
New-Item -Path ".\notes.txt" -ItemType "File"
Get-Content -Path ".\notes.txt"
```

---

#### Piping, Filtering, and Sorting

PowerShell pipes objects, not just text.

**Common pipeline cmdlets:**

| **Cmdlet**      | **Purpose**                          |
|-----------------|--------------------------------------|
| `Sort-Object`   | Sort results                         |
| `Where-Object`  | Filter results                       |
| `Select-Object` | Select specific properties           |
| `Select-String` | Search for text patterns (like grep) |

**Useful comparison operators:**
- `-eq` → equal to
- `-ne` → not equal to
- `-gt` / `-ge` → greater than / greater than or equal
- `-lt` / `-le` → less than / less than or equal
- `-like` → pattern match

**Examples:**

``` PowerShell
# List only .txt files
Get-ChildItem | Where-Object -Property Extension -eq ".txt"

# Sort files by size
Get-ChildItem | Sort-Object Length

# Show only Name and Length
Get-ChildItem | Select-Object Name, Length

# Find the largest file
Get-ChildItem | Sort-Object Length -Descending | Select-Object -First 1

```

---

#### System and Network information
| **Cmdlet**               | **Purpose**                 |
|--------------------------|-----------------------------|
| `Get-ComputerInfo`       | Detailed system information |
| `Get-LocalUser`          | List local user accounts    |
| `Get-NetIPConfiguration` | Network interface details   |
| `Get-NetIPAddress`       | IP address information      |

---

#### Real-Time System Analysis

| **Cmdlet**             | **Purpose**                                        |
|------------------------|----------------------------------------------------|
| `Get-Process`          | List running processes                             |
| `Get-Service`          | List services and their status                     |
| `Get-NetTCPConnection` | Show active TCP connections                        |
| `Get-FileHash`         | Generate file hashes (useful for integrity checks) |

**View Alternate Data Streams (ADS):**
``` PowerShell
Get-Item -Path "C:\path\to\file.txt" -Stream *
```

This allows you to run commands or scripts on remote systems.

---

**End of Room 2**
  
</details> <!-- Ends Room 2-->

---

<details> <!-- Starts Room 3-->
<summary><strong>Room 3 - Linux Shells</strong></summary>

### Room 3 - Linux Shells

**Learning Objectives**
- Interact with a Linux shell
- Use basic shell commands
- Understand the main types of Linux shells
- Write simple shell scripts using variables, loops, and conditionals

---

#### Basic Shell Interaction

| Command | Purpose |
|---------|---------|
| `pwd` | Print current working directory |
| `cd <directory>` | Change directory |
| `ls` | List directory contents |
| `cat <file>` | Display file contents |
| `grep <pattern> <file>` | Search for a pattern inside a file |

**Examples:**
```bash
pwd
cd Desktop
ls
cat filename.txt
grep THM dictionary.txt
```

---

#### Types of Linux Shells

**Check your current shell:**

```Bash
echo $SHELL
```

**List available shells:**

```Bash
cat /etc/shells
```

**Switch to another shell:**

```Bash
zsh
```

**Common shells:**  

| **Shell** | **Full Name**              | **Key Features**                                                         |
|-----------|----------------------------|--------------------------------------------------------------------------|
| Bash      | Bourne Again Shell         | Default on most systems, good scripting, tab completion, command history | 
| Fish      | Friendly Interactive Shell | Very user-friendly, auto-suggestions, syntax highlighting                |
| Zsh       | Z Shell                    | Highly customizable, advanced tab completion, plugins (oh-my-zsh)        |

---

#### Shell Scripting Basics

A shell script is a file containing a series of commands.

Scripts usually end with `.sh`.

**Shebang (first line of every script):**

```Bash
#!/bin/bash
```

**Make a script executable:**

```Bash
chmod +x script_name.sh
```

**Run the script:**

```Bash
./script_name.sh
```

---

#### Script Components

1. Variables
```Bash
#!/bin/bash
echo "What is your name?"
read name
echo "Welcome, $name"
```

2. Loops
```Bash
#!/bin/bash
for i in {1..10}; do
  echo $i
done
```

3. Conditional Statements
```Bash
#!/bin/bash
echo "Enter your name:"
read name

if [ "$name" = "Stewart" ]; then
  echo "Welcome Stewart! Here is the secret: THM_Script"
else
  echo "Sorry! You are not authorized."
fi
```

4. Comments
```Bash
# This is a comment
```

---

#### Example: Locker Script

A simple authentication script that checks username, company, and PIN.

```Bash
#!/bin/bash

username=""
companyname=""
pin=""

for i in {1..3}; do
  if [ "$i" -eq 1 ]; then
    echo "Enter your Username:"
    read username
  elif [ "$i" -eq 2 ]; then
    echo "Enter your Company name:"
    read companyname
  else
    echo "Enter your PIN:"
    read pin
  fi
done

if [ "$username" = "John" ] && [ "$companyname" = "Tryhackme" ] && [ "$pin" = "7385" ]; then
  echo "Authentication Successful. You can now access your locker, John."
else
  echo "Authentication Denied!!"
fi
```

---

Practical Notes

Always start scripts with the correct shebang (`#!/bin/bash`)
- Give execution permission with `chmod +x`
- Use variables to store values
- Use loops for repetitive tasks
- Use `if` statements for decision-making
- Add comments to make scripts easier to understand


---

***End of Room 3**

  
</details> <!-- Ends Room 3-->


























  
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
<summary><strong>Module 5: Networking - Currently Working On</strong></summary>

---

<details>
<summary><strong>Room 1 - Networking Concepts</strong></summary>

  *Notes to come*
  
</details> <!-- End Room 1 -->

---

<details>
<summary><strong>Room 2 - Networking Essentials</strong></summary>

  *Notes to come*
  
</details> <!-- End Room 2 -->

---

<details>
<summary><strong>Room 3 - Networking Core Protocols</strong></summary>

  *Notes to come*
  
</details> <!-- End Room 3 -->

---

<details>
<summary><strong>Room 4 - Networking Secure Protocols</strong></summary>

  *Notes to come*
  
</details> <!-- End Room 4 -->

---

<details>
<summary><strong>Room 5 - Wireshark: The Basics</strong></summary>

  *Notes to come*
  
</details> <!-- End Room 5 -->

---

<details>
<summary><strong>Room 6 - Tcpdump: The Basics</strong></summary>

  *Notes to come*
  
</details> <!-- End Room 6 -->

---

<details>
<summary><strong>Room 7 - Namp: The Basics</strong></summary>

  *Notes to come*
  
</details> <!-- End Room 7 -->

---




































  
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
