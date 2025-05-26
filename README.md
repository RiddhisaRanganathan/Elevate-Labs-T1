# Elevate-Labs-T1 - Local Network Port Scan Report

## Task Overview
This repository contains the results of a TCP SYN port scan performed on the local network IP range 192.168.1.0/24 using Nmap. The scan was done to identify open ports on devices in the network to understand potential network exposure.

## Common Services Found and Their Risks

| Port  | Service         | Description                                      | Potential Security Risks                                                      |
|-------|-----------------|------------------------------------------------|-------------------------------------------------------------------------------|
| 22    | SSH             | Secure remote login protocol                     | Weak passwords or outdated versions may allow unauthorized access.           |
| 80    | HTTP            | Hypertext Transfer Protocol for web traffic     | Vulnerable to web attacks like XSS, SQL injection if unpatched or misconfigured. |
| 443   | HTTPS           | Secure HTTP using SSL/TLS                        | Misconfiguration or outdated SSL/TLS can expose encrypted traffic to risks.  |
| 21    | FTP             | File Transfer Protocol                           | Unencrypted credentials vulnerable to interception; susceptible to brute force attacks. |
| 25    | SMTP            | Simple Mail Transfer Protocol for sending email | Can be abused for spam relay or phishing if not secured properly.             |
| 53    | DNS             | Domain Name System service                        | Vulnerable to DNS spoofing and cache poisoning if insecure.                   |
| 110   | POP3            | Post Office Protocol for email retrieval         | Unencrypted communication can lead to credential interception.               |
| 143   | IMAP            | Internet Message Access Protocol for email       | Same risks as POP3 regarding unencrypted data and interception.               |
| 3389  | MS-WBT-Server   | Microsoft Remote Desktop Protocol (RDP)          | Risk of unauthorized remote access if weak passwords or unpatched software.   |

## Nmap Scan

### Description
A TCP SYN scan was performed on the IP range `192.168.50.0/24` using Nmap 7.97. This scan helped identify open ports and running services on devices in the network.
### Procedure: 
- The scan was done with the command: nmap -sS -oN scanresult.txt 192.168.50.0/24
- The results are saved in the file `scanresult.txt` included in this repository.

## Wireshark Capture

### Description
Packet capture was performed on the local network interface using Wireshark to analyze network traffic patterns, protocols in use, and identify any suspicious activity.

### Procedure:
- The captured packets were filtered and analyzed using Wireshark with the command: tcp || ip.src == <my_ip> || ip.dst == <my_ip>
#### What packets are observed in this capture?
- **SYN packets sent by the scanning device**: These are the initial connection requests sent to target ports to check if they are open.
- **SYN-ACK packets from the target device**: If a target port is open, the device responds with a SYN-ACK, indicating readiness to establish a connection.
- **RST packets sent by the scanning device**: Instead of completing the TCP handshake with an ACK, Nmap sends a RST (reset) packet to terminate the connection immediately. This keeps the scan "stealthy" and prevents full connection establishment.
- 
## Privacy and Spoofing
- IP addresses and MAC addresses are spoofed for security reasons.
