# Enumeration and Foothold Tutorial

## Enumeration

The process begins with scanning the target once connected to the VPN. Use the following nmap command to scan all ports and display service versions:


nmap -sV <target-ip>


- `-sV`: Probes open ports to determine service/version info.

![image](https://github.com/TheCyberVault/CTFs/assets/141572056/583d953a-1b42-43ed-a3da-3adf20f50944)

We notice that port 445 (TCP) for SMB is active, indicating a potential share to explore. To access this share, we'll need smbclient, a script for enumerating SMB shares.

### Installing smbclient

If smbclient is not installed, you can install it on Debian-based systems with:


sudo apt-get install smbclient


![image](https://github.com/TheCyberVault/CTFs/assets/141572056/86d204f3-7974-4798-b2a7-aee8584f7793)

Once installed, we use smbclient to enumerate the share's contents. smbclient will check for authentication requirements. If none, it may allow guest or anonymous access to view the share's files.

### Using smbclient

To connect to the remote share:

smbclient //<target-ip>/sharename


- If prompted for a password, leave it blank and press Enter to attempt anonymous access.

![Smbclient Usage](path/to/your/smbclient_usage_image.png)

Use `-L` with smbclient to list available shares:

smbclient -L //<target-ip>

We discover shares like ADMIN$, C$, IPC$, and custom shares like WorkShares.

![Smbclient Shares](path/to/your/smbclient_shares_image.png)

## Foothold

We attempt to connect to each share, except IPC$, using smbclient without credentials to find misconfigured permissions.

### Accessing Shares

Attempts to access ADMIN$ and C$ yield `NT_STATUS_ACCESS_DENIED`. However, connecting to WorkShares is successful.

![WorkShares Access](path/to/your/workshares_access_image.png)

Within the smb shell, we use common commands to navigate and download files:

- `ls`: List directory contents.
- `cd`: Change directories.
- `get`: Download files.
- `exit`: Exit the smb shell.

Exploring the directories, we find `worknotes.txt` in Amy.J's directory and `flag.txt` in James.P's directory. We use `get` to download these files.

![SMB Shell](path/to/your/smb_shell_image.png)

### Analyzing Files

After exiting the smb shell, we examine the downloaded files. `worknotes.txt` might contain hints for further exploration, while `flag.txt` contains the required flag.

![File Analysis](path/to/your/file_analysis_image.png)

Upon reviewing `flag.txt`, we submit the flag to complete the task for the Dancing machine.



