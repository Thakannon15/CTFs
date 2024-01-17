# CTF Challenge Report: Exploiting the Telnet Service

## Executive Summary
This report details my approach and methodology in successfully completing a CTF challenge focused on exploiting the Telnet service. The process began with a ping scan to ensure connectivity, followed by a comprehensive `nmap` scan using both `-sV` and `-sC` options for service identification and running default scripts, respectively. This exercise was part of a Hack The Box scenario, aimed at demonstrating practical skills in cybersecurity, particularly in network exploitation.

## Objective
The primary goal was to exploit vulnerabilities in the Telnet service of a target system to retrieve a hidden flag, indicative of successful system access.

## Tools and Technologies Used
- **VPN**: For establishing a secure connection.
- **Ping Scan**: Initial connectivity check with the target.
- **Nmap**: Advanced network scanning, service identification, and running default scripts.
- **Telnet Client**: To access and interact with the target service.

## Methodology
### Reconnaissance
- Established a secure VPN connection.
- Conducted a ping scan to verify connectivity with the target.
- Performed an `nmap` scan with `-sV` for service identification and `-sC` for executing default scripts.
- `nmap` Commands Used: `nmap -sV -sC {target_IP}`

### Exploitation Attempt
- Accessed the Telnet service using the command: `telnet {target_IP}`
- Experimented with multiple common credentials to log into the Telnet service.
- Gained access after several attempts.

### Flag Retrieval
- Navigated the file system using command line.
- Located and accessed the `flag.txt` file.
- Command Used: `cat flag.txt`

## Challenges and Solutions
- **Challenge**: Initial difficulty in accessing the Telnet service with common credentials.
- **Solution**: Persistence and creative thinking in trying different username-password combinations led to eventual access.

## Outcome
Successfully retrieved the flag from the target system, indicating full exploitation of the Telnet service vulnerability.
