## What
Ports are logical Communication endpoints used by services.

## Why it matters
Attackers target exposed ports to gain access.

Example:
Port 3389 open -> Possible RDP exposure -> brute force risk .

## Common Ports and Protocols

21 - FTP (File Transfer Protocol)
- Unencrypted file transfer.
- Generally insecure; Should be replaced by SFTP

22 - SSH (Secure Shell)
- Used for secure remote logins and file transfers (SFTP).
- Heavily targeted for brute force attacks.

23 - Telnet
- Unencrypted remote Login
- Should be completely disabled in the favor of SSH.

25 - SMTP (Simple Mail Transfer Protocol)
- The Protocol used to transfer email from a client to an email server; it is also used to transfer email between servers

53 - DNS (Domain Name System)
- Resolves hostnames to IP addresses.
- Used in DNS amplification attacks.

80 - HTTP (Hyper Text Transfer Protocol)
- The primary protocol used to transfer data over the internet

110 - POP3 (Post Office Protocol v3)
- The protocol used by clients to retrieve email from servers. Once engaged, POP3 downloads all messages from the severs. The user cannot access email messages until they have been downloaded

143 - IMAP (Internet Message access Protocol)
- A protocol used by clients to access email servers. Allows the clients to administrator and organize email on the server into folders.

443 - HTTPS (Hyper Text Transfer Protocol Secured)
- Encrypted web traffic using SSL/TLS. 
- Essential for secure communication

445 - SMB (Server Message Block)
- Used for windows file sharing and Active directory.
- Vulnerable to exploits like Vulnerable cry.

1433/1434 - MS-SQL
- Microsoft SQL server Database.
- Targeted for database breaches

3306 - MySQL
- MySQL Database.
- Targeted for unauthorized database access.

3389 - RDP (Remote Desktop protocol)
- Windows remote access .
- A top target for ransomware and unauthorized attacks 

## Essential Network Services

67/68 - DHCP (Dynamic Host Configuration Protocol)
- Automatically assigns IP addresses.

123 - NTP (Network Time Protocol)
- Synchronize Computer clocks.

137-139 - NetBIOS(Network basic input and output System)
- Legacy Windows Network services.
- Originally developed to allow hosts to be able to communicate with servers

161/162 - SNMP (Simple Network Management Protocols)
- Manages Network devices.

## High-Risk Ports for SOC

22 - SSH
- Watch for repeated login Failures

3389 - RDP
- Extremely Targeted by Attackers.

445 - SMB
- Common  in lateral movement and ransomware.

80 / 443 - Web Traffic
- Look for unusual Port Request or Spikes

53 - DNS
- Malware often uses DNS Beaconing

## How to Detect
- Firewall Logs
- SIEM alerts
- Authentication Logs

## SOC Response
1. Check Source IP.
2. Look for repeated Attempts.
3. Geo-Location Anomalies.
4. Time - Patterns.

## Interview Angle
" Open Ports expand the attack surface. SOC teams monitor them because attackers typically scan before attempting exploitations "