## Executive Summary
This report outlines the methodology and results of a Capture The Flag (CTF) challenge that focused on exploiting the File Transfer Protocol (FTP) service, conducted on the Hack The Box platform. The challenge was a practical exercise in applying cybersecurity techniques for network enumeration and exploitation, with a particular emphasis on understanding and leveraging vulnerabilities within the FTP service.

## Objective
The primary aim was to exploit weaknesses in the FTP service of a target system, with the ultimate goal of retrieving a specific file (`flag.txt`), indicative of successful penetration and data extraction.

## Tools and Technologies Used
- **VPN**: Used for establishing a secure connection to the target.
- **Ping**: For initial connectivity check with the target.
- **Nmap**: Employed for network scanning and identifying the open FTP service.
- **FTP Client**: Utilized to interact with and exploit the target's FTP service.

## Methodology
### Initial Setup and Reconnaissance
- Established a VPN connection to securely access the target network.
- Conducted a ping scan to ensure the target was reachable.
- Performed an `nmap` scan to identify open services, particularly focusing on the FTP service running on port 21.

### Service Exploration and Exploitation
- Verified and updated the local FTP client for interaction with the target.
- Connected to the target's FTP service using the `ftp {target_IP}` command.
- Investigated the FTP service configuration, discovering an anonymous login capability due to a common misconfiguration.

### Data Retrieval and Analysis
- Accessed the FTP service with 'anonymous' credentials, successfully bypassing standard authentication.
- Utilized standard FTP commands to navigate the directory and identify important files.
- Retrieved the target file (`flag.txt`) using the `get` command, effectively downloading it to the local system.

## Challenges and Solutions
- **Challenge**: Identifying an effective method to access and exploit the FTP service.
- **Solution**: Utilized reconnaissance data to leverage the misconfigured anonymous login capability of the FTP service.

## Outcome
Successfully exploited the FTP service misconfiguration to retrieve the desired file, demonstrating the ability to identify and exploit common network service vulnerabilities.

## Conclusion
This CTF challenge illustrated the importance of thorough reconnaissance and the exploitation of service misconfigurations in network penetration. It underscored key skills in network scanning, vulnerability assessment, and strategic exploitation, crucial for effective cybersecurity practices.
