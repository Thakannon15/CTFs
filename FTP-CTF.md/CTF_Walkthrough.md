# HTB: Exploiting the FTP Protocol

## Introduction
This lab walkthrough is part of a penetration testing series focusing on various phases of a security audit. In this segment, we'll cover exploiting the FTP (File Transfer Protocol) service, a common target in network penetration tests.

## Lab Steps

### 1. Establishing VPN Connection
Before starting, ensure your VPN connection is active. This is crucial for creating a secure channel to interact with the target system.

### 2. Initial Ping Test
- Once the VPN is active, start by pinging the target's IP address. 
- Obtain the target's IP from your lab materials.
- Use the command: `ping [target_IP]`.
- Look for successful replies to confirm a stable connection.
- Terminate the ping command with `CTRL+C` when done.

![Ping Test](https://github.com/ThiasCannon/CTFs/assets/141572056/0e9380b7-d954-4953-81a6-1520443ae8ce)

### 3. Port Scanning with Nmap
- Now, use `nmap` to scan the target's open ports. 
- This helps identify running services on the target, including FTP.
- Use the command: `nmap -sV {target_IP}`.
- Replace `{target_IP}` with your target's actual IP address.
- Analyze the `nmap` output for open ports and running services, especially for FTP running on port 21.

![Port Scan](https://github.com/ThiasCannon/CTFs/assets/141572056/6944b147-2e7e-4b8a-b45a-778468361902)


### 4. Connecting to FTP Service
- If FTP is open, attempt to connect to the target using FTP.
- Use the command: `ftp {target_IP}`.
- Try logging in as an anonymous user, a common misconfiguration in FTP services.
- Use 'anonymous' as the username and any password (if required).

![Connecting to FTP](https://github.com/ThiasCannon/CTFs/assets/141572056/9ed198f5-d61f-484c-bed6-9770522962ea)



### 5. Exploring FTP Contents
- Once logged in, explore the FTP server's contents.
- Use commands like `ls` to list files and `cd` to navigate directories.
- Look for the file named `flag.txt` or other interesting files.

![FTP Nav](https://github.com/ThiasCannon/CTFs/assets/141572056/67fc4540-7256-4b76-b777-22cd12bfbddf)


### 6. Retrieving the Flag
- If you find `flag.txt`, use the `get` command to download it.
- Use the command: `get flag.txt`.
- This will download the file to your local machine.

![Credential Gathering](https://github.com/ThiasCannon/CTFs/assets/141572056/a5f3d7ba-a25b-464d-9f8c-dfd240297e34)


### 7. Documenting Findings
- Record all findings, including methods used for accessing the FTP server, files discovered, and the contents of the `flag.txt` file.
- Maintain a structured format for easy reference in later phases of the penetration test.

## Conclusion
Successfully exploiting the FTP service demonstrates a critical skill in penetration testing - the ability to identify and leverage service misconfigurations. It provides the necessary information for further exploitation and system access. Always ensure you have legal authorization before engaging in penetration testing activities.
