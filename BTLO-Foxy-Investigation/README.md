🔐 BTLO — FOXY Investigation
<img width="889" height="758" alt="Screenshot 2026-03-22 at 13 05 53" src="https://github.com/user-attachments/assets/d1fbcfb1-98c7-4335-a302-72042e8ba6f2" />

---

Summary: 
Analysis of multiple indicators revealing malware activity, C2 beaconing (Cobalt Strike), Discord-based payload distribution, and Log4Shell exploitation attempts.

---

⚔️ Key Findings:

1️⃣ C2 Beaconing (Cobalt Strike):
        Indicator: `/dot.gif` → 45.63.126.199  
        ➡️ Repeated outbound connections from multiple hosts  
        ➡️ Behaviour consistent with beaconing

---

2️⃣ Malware Identification:
        SHA256 linked to IRATA (Android spyware)  
        ➡️ Confirmed via MalwareBazaar

---

3️⃣ Spyware Activity (Collection):
        - Access Contact List  
        - Capture SMS Messages  
        - Location Tracking  
        ➡️ Sensitive data collection behaviour

---

4️⃣ C2 Infrastructure:
        Domain: uklivemy.gq  
        IP: 20.238.64.240  
        ➡️ External attacker-controlled infrastructure

---

5️⃣ Suspicious C2 Ports:
        IP: 192.236.198.236  
        Ports: 1505, 1506  
        ➡️ Non-standard ports commonly used for C2

---

6️⃣ Malware Delivery Chain:
        Weaponized document drops JAR payload  
        ➡️ Indicates execution stage of malware

---

7️⃣ Discord CDN Abuse:
        https://cdn.discordapp.com/attachments/  
        ➡️ Legitimate service used for malware hosting

---

8️⃣ Malware Campaign:
        Dridex observed across multiple entries  
        ➡️ Indicates widespread distribution

---

9️⃣ Exploitation Attempt:
        IP: 107.172.214.23:8001  
        CVE: CVE-2021-44228 (Log4Shell)  
        ➡️ Remote Code Execution attempt detected

---

🛠️ Tools:

        grep • wc • less  
        MalwareBazaar  
        JoeSandbox  
        ThreatFox dataset  

---

🚨 Verdict:
        
        True Positive — Confirmed malicious activity across multiple indicators

---

💡 Key Insight

        Multiple independent indicators (C2, malware, exploitation, hosting abuse) confirm active malicious activity rather than benign traffic.
