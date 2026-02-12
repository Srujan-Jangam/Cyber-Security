## Summary

Simulated authentication failures, invalid username attempts, successful login after repeated failures, and privileged command execution on a Linux system (Kali & Metasploitable) to analyze detection patterns in system logs.

---

## Log Sources Observed

- `journalctl` (systemd journal – Kali)
    
- `/var/log/auth.log` (Metasploitable)
    
- LightDM logs (GUI authentication events)

---

## Event Sequence Observed

### 1️⃣ Invalid Username Attempt

- Authentication failure for unknown user.
    
- Indicates username enumeration behavior.
    
- Logged in journal (authentication failure entries).
    

### 2️⃣ Multiple Failed Login Attempts (Valid User)

- Repeated authentication failures within short time interval.
    
- Pattern consistent with brute-force behavior.
    
- Logged in:
    
    - `journalctl`
        
    - LightDM (GUI login attempts)

### 3️⃣ Successful Login After Failures

- Successful authentication for previously targeted user.
    
- Occurred immediately after repeated failures.
    
- High-risk pattern in real environments (possible credential compromise).


### 4️⃣ Privileged Command Execution (sudo)

- Executed `sudo` commands post-login.
    
- Logged in:
    
    - `journalctl` (Kali)
        
    - `/var/log/auth.log` (Metasploitable)
        
- Included invoking user, TTY/PTS source, and executed command.


---

## Risk Escalation Analysis

|Event Type|Risk Level|Reason|
|---|---|---|
|Single failed login|Low|Likely user error|
|Multiple failures|Medium|Possible brute-force attempt|
|Failures → Success|High|Possible credential compromise|
|Success → sudo activity|Critical|Potential privilege escalation|

---

## Key Observations

- Authentication logs vary across systems (journal vs auth.log).
    
- GUI login attempts appear in LightDM logs.
    
- TTY context indicates login source (local vs remote).
    
- Privileged activity significantly increases incident severity.
    
- Event **sequence** is more important than isolated events.


---

## SOC-Relevant Insight

Risk must be evaluated based on:

- Timing
    
- Sequence of events
    
- Account targeted
    
- Privilege escalation attempts