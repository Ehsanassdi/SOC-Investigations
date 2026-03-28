BTLO — COUNTDOWN Investigation
<img width="874" height="751" alt="Screenshot 2026-03-28 at 13 08 28" src="https://github.com/user-attachments/assets/3d223a27-b1da-4212-bd2e-e61f15bd0b43" />


Summary:

        Digital forensics investigation uncovering attacker communication, email-delivered payload, hidden artefacts, and encoded intelligence revealing a planned attack (time and GPS location).


Attack Chain:

1️⃣ Initial Access (Email Attachment)
        Suspicious email identified in chat logs
        Attachment received and executed by user
        
➡️ Indicates phishing-based initial access


2️⃣ User Execution

        Artefact: .lnk file (Recent Documents)
        Opened file:
        ⏳📅.PNG
        
➡️ Confirms user interaction with malicious attachment
        

3️⃣ Encrypted Communication

        Application: Signal
        Extracted decryption key from config file
        Decrypted messaging database
        
➡️ Indicates use of secure messaging for coordination
        

4️⃣ Data Exchange

        Extracted email from chat:
        eekur@babybabes.com

➡️ Evidence of external communication / coordination
        

5️⃣ Timeline Reconstruction

        Artefact: thumbcache_256.db
        Tool: Thumbcache Viewer
    
        Recovered image showing:
        
        01-02-2021 09:00 AM
        
➡️ Reveals planned attack date & time
        

6️⃣ Hidden Intelligence (Encoded Data)

        Source: Sticky Notes database (plum.sqlite)
        Table: Note
        Found encoded GPS coordinates

➡️ Indicates intentional obfuscation
        

7️⃣ Decryption & Location Discovery

        Identified encoding via Tor browser history
        Method: ROT13 (CyberChef)
        
        Decoded result:
        
        40 degrees 45 minutes 28.6776 seconds N, 73 degrees 59 minutes 7.944 seconds W
        ➡️ Reveals exact blast location
        

Tools Used:

        - Autopsy
        - DB Browser for SQLite
        - Thumbcache Viewer
        - CyberChef

  
Key Findings:

        - Phishing email used for initial access
        - Malicious attachment executed by user
        - Encrypted messaging (Signal) used by attacker
        - Attack date & time recovered from thumbnail cache
        - GPS coordinates hidden in Sticky Notes
        - ROT13 encoding used for obfuscation
        
        
Verdict:

        True Positive — Confirmed malicious activity involving email delivery, user execution, encrypted communication, and planned physical attack.

        
Key Insight:

        Correlation of artefacts (email + .lnk + thumbcache + SQLite + encoding) reveals full attack lifecycle including execution, timing, and location.
