🔐 BTLO — ANAKUS Investigation  
<img width="872" height="746" alt="Screenshot 2026-03-26 at 12 42 48" src="https://github.com/user-attachments/assets/03226464-3567-4ca7-b7a7-7513a55acf02" />

Summary:
Analysis of SIEM alerts revealing authentication attacks, PowerShell activity, privilege manipulation, and persistence techniques within a Windows environment.

---

⚔️ Attack Chain  

1️⃣ Initial Access (Password Spraying):  
        Multiple login attempts from a single IP across many users  
        ➡️ Indicates password spraying activity  

---

2️⃣ Authentication Attack:  
        - High volume of login attempts  
        - Same source IP targeting multiple accounts  
        ➡️ Credential access attempt  

---

3️⃣ Privilege & Account Activity:  
        - Local user accounts created  
        - Security principal manipulation detected  
        ➡️ Potential privilege escalation / account abuse  

---

4️⃣ Command Execution (PowerShell):  
        - Potentially malicious PowerShell activity detected  
        ➡️ Possible script-based execution or post-exploitation  

---

5️⃣ Persistence Mechanism:  
        - WMI(Windows Management Instrumentation) Persistence observed  
        ➡️ Attacker maintaining long-term access  

---

6️⃣ Defense Evasion:  
        - Log files cleared (Event ID 1102)  
        ➡️ Attempt to hide activity  

---

🧰 Tools Used:  

        - SIEM (Timeline Explorer)  
        - grep / wc / less  
        - Log analysis techniques  

---

📌 Key Findings : 

        - Password Spraying attack detected  
        - Suspicious PowerShell execution  
        - Account creation and privilege manipulation  
        - WMI(Windows Management Instrumentation) persistence established  
        - Logs cleared to evade detection  

---

🚨 Verdict:  

        True Positive — Confirmed malicious activity involving authentication attacks, execution, persistence, and defense evasion  

---

💡 Key Insight:  

        Multiple correlated alerts (password spray + PowerShell + persistence + log clearing) confirm attacker progression across the kill chain.
