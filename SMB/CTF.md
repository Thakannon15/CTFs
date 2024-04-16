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

Use `-L` with smbclient to list available shares:

- If prompted for a password, leave it blank and press Enter to attempt anonymous access.

![Smbclient Usage](https://github.com/TheCyberVault/Capture-The-Flags/assets/141572056/39030a64-7b55-4db9-b6db-f13df5736afd)

We discover shares like ADMIN$, C$, IPC$, and custom shares like WorkShares.

![Smbclient Usage](https://github.com/TheCyberVault/Capture-The-Flags/assets/141572056/39030a64-7b55-4db9-b6db-f13df5736afd)

## Foothold

We attempt to connect to each share, except IPC$, using the command `smbclient \\\\{target_IP}\\share name` without credentials to find misconfigured permissions with smbclient.

### Accessing Shares

Attempts to access ADMIN$ and C$ yield `NT_STATUS_ACCESS_DENIED`. However, connecting to WorkShares is successful.

![Accessing Shares](https://github.com/TheCyberVault/Capture-The-Flags/assets/141572056/4b40c8ce-654f-4163-a926-487a8a18291d)


Within the smb shell, we use common commands to navigate and download files:

- `ls`: List directory contents.
- `cd`: Change directories.
- `get`: Download files.
- `exit`: Exit the smb shell.

Exploring the directories, we find `worknotes.txt` in Amy.J's directory and `flag.txt` in James.P's directory. We use `get` to download these files.

![Amy.J](https://github.com/TheCyberVault/Capture-The-Flags/assets/141572056/ebb801a6-da0e-4693-a702-9c34f7aeb50d)

![James.P](https://github.com/TheCyberVault/Capture-The-Flags/assets/141572056/a5b63913-26f5-4188-8766-d653b806ec97)


### Analyzing Files

After exiting the smb shell, we examine the downloaded files. `worknotes.txt` might contain hints for further exploration, while `flag.txt` contains the required flag.

![File Analysis](https://github.com/TheCyberVault/Capture-The-Flags/assets/141572056/710d38d6-30e2-4f37-86b0-a7ef72f94f1f)


Upon reviewing `flag.txt`, we submit the flag to complete the task for the Dancing machine.



