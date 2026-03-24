# FICBANK Security Event and Incident Report

📄 Full Report: [View PDF](./FICBANK-Security-Event-and-Incident-Report.pdf)

## Overview
This project simulates a real-world cybersecurity investigation within a financial institution (FICBANK). The objective was to identify indicators of compromise (IoCs) by analyzing log data, network traffic, and file artifacts.

## Tools Used
- Wireshark (PCAP analysis)
- PowerShell (log analysis)
- TrID (file type verification)

## Key Findings
- Repeated access from unknown external IP addresses indicating automated scanning activity
- Suspicious URL paths associated with probing and exploitation attempts
- High volume of HTTP 400 errors suggesting malformed or malicious requests
- Unauthorized HTTP POST file uploads to the server
- Files disguised as .jpg that contained unknown or executable characteristics

## Investigation Breakdown

### Log Analysis (PowerShell)
- Identified repeated requests from external IPs such as:
  - 80.82.70.24
  - 198.20.69.74
  - 95.213.177.122
- Detected abnormal request paths including:
  - /robots.txt
  - /xmlrpc.php
  - testproxy.php
- Observed high volumes of HTTP 400 and 404 errors indicating probing activity

### Network Traffic Analysis (Wireshark)
- Analyzed HTTP streams within PCAP data
- Identified suspicious external IP attempting file uploads:
  - 61.161.130.241
- Detected multiple HTTP POST upload attempts:
  - /OSKI/1.JPG
  - /OSKI/2.JPG
  - /OSKI/3.JPG
- Behavior indicated potential malicious payload delivery

### File Analysis (TrID)
- Verified extracted files from network traffic
- Discovered multiple files did not match JPEG signatures
- Identified unknown file types and possible executable characteristics
- Confirmed files were disguised to bypass detection mechanisms

## Outcome
The investigation confirmed that FICBANK experienced automated scanning, probing, and attempted malicious file uploads. Multiple indicators of compromise were identified across logs, network traffic, and file artifacts, suggesting a coordinated attack attempt.

## Skills Demonstrated
- Threat detection and analysis
- Network traffic investigation
- Log correlation and analysis
- Incident response documentation
- Indicator of Compromise (IoC) identification
