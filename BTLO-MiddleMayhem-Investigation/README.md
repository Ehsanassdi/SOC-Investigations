🔐 BTLO — MiddleMayhem Investigation
<img width="920" height="758" alt="Screenshot 2026-03-17 at 16 46 37" src="https://github.com/user-attachments/assets/dde996e0-74ee-43a8-a406-9ae71fdea9b1" />


🧠 Summary
Multi-stage web attack leading to full system compromise, including RCE (Remote Code Execution) and lateral movement.


⚔️ Attack Chain

1️⃣ Recon:

        Next.js 15.0.0
        
        /admin, /admin/file-upload


2️⃣ Exploitation:

        CVE-2025-29927
        
        Header: x-middleware-subrequest
        ➡️ Authorization bypass


3️⃣ Web Shell:
        
        POST /api/upload
        
        shell.sh
        ➡️ Command execution


4️⃣ Reverse Shell (C2):

        113.89.232.157:31337
        ➡️ Remote control


5️⃣ Lateral Movement:

        SSH brute force
        
        User: dbserv
        ➡️ Access to another system


Tools:

        Splunk • Browser • NVD (National Vulnerability Database)


Verdict:
        True Positive — Full Compromise


Key Insight:
        Upload + reverse shell + login success
        ➡️ Real compromise, not scanning
