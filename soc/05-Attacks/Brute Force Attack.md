
### What It Is ###
A brute force attack is a password-guessing technique where attackers repeatedly attempt authentication until the correct credentials are found.

---
### What Happens

Successful brute force attacks lead to account compromise and unauthorized system access.

Early detection prevents breaches.

---
### What It Looks Like in Logs 

**Primary Detection Pattern:**

- Multiple failed login attempts
- Occurring within a short timeframe
- Targeting the same account

**Critical Red Flag:**  
	 Failed attempts followed by a **successful login**

Treat as potential compromise.

---
### Common Variants

- Dictionary attack → common passwords
- Credential stuffing → reused leaked passwords
- Password spraying → one password across many users

---
### Investigation Flow

If alert triggers:

1. Check authentication logs  
2. Count failed attempts  
3. Identify targeted account  
4. Look for success after failures  
5. Determine source (local / remote)  
6. Escalate if compromise suspected

---
### Risk Level

Few failures → likely user mistake  
Many failures → suspicious  
Failures + success → HIGH RISK

---
### Prevention Awareness
- MFA
- Strong passwords
- Rate limiting
- Account lockouts