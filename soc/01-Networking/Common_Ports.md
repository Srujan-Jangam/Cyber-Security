## What
Ports are logical Communication endpoints used by services.

## Why it matters
Attackers target exposed ports to gain access.

Example: 
Port 3389 open -> Possible RDP exposure -> brute force risk .

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