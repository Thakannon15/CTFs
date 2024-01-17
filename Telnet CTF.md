# HTB Telnet CTF

# Lab Steps

### Step 1: Establishing VPN Connection
To begin, make sure your VPN is connected. This step is essential to securely access the target network.

### Step 2: Ping Test
First, we'll check if the target system is reachable via your network.

- Obtain the target IP address from your lab materials.
- Use the `ping` command as follows:

```bash
ping [target_IP]
```

- Look for replies indicating a stable connection.
- Interrupt the ping process using `CTRL+C`.

![Ping Test](https://github.com/ThiasCannon/CTFs/assets/141572056/6c1c1c9b-b647-430a-9370-72ab5fd74862)



### Step 3: Scanning with Nmap
Next, we'll use `nmap` to identify open ports and services on the target.

```bash
# Replace {target_IP} with the actual IP address
nmap -sV {target_IP}
```

- Analyze the scan results to understand the target's network landscape.

![Nmap Scan Results](https://github.com/ThiasCannon/CTFs/assets/141572056/4338d44c-a1a1-408f-b1be-7cc6da88205e)

### Step 4: Exploring Services
Identify key services and potential vulnerabilities from the `nmap` output.

- Pay special attention to common services like HTTP, FTP, or Telnet.

### Step 5: Telnet Access Attempt
If Telnet is available, try accessing the target using it.

```bash
# Attempt to connect via telnet
telnet {target_IP}
```

- Experiment with common usernames like `admin`, `administrator`, or `root`.
- Remember, persistence is key in penetration testing!

![Telnet Access Attempt](https://github.com/ThiasCannon/CTFs/assets/141572056/28b7ddcc-32d4-4dc0-acc5-8ca43d636d15)

![Telnet Access Attempt](https://github.com/ThiasCannon/CTFs/assets/141572056/9a2906fa-26ab-42d1-8e86-ffd0af9d391b) 

### Step 6: Gaining Access
Once inside the system, explore the directory to find sensitive files.

```bash
# List contents of the current directory
ls
```

- Search for files like `flag.txt` or `user.txt` that may contain valuable information.

![Gaining Access](https://github.com/ThiasCannon/CTFs/assets/141572056/83cf53cd-a99f-440b-b2c8-13a59ca5ee15)


### Step 7: Documentation
Document all your findings systematically.

- Note down the open ports, identified services, and any successful access attempts.

## Conclusion
This lab aims to give you a hands-on experience in enumeration, a vital skill in cybersecurity. Remember, ethical hacking should always be practiced responsibly and legally. Happy learning!
