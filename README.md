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

## Scan Results
- Results saved in `scanresult.txt` (included in this repo).

## Privacy and Spoofing
- IP addresses and MAC addresses are spoofed for security reasons.
