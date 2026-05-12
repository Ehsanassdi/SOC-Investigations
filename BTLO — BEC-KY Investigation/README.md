BTLO — Bec-ky Investigation (Business Email Compromise Analysis)
<img width="811" height="708" alt="Screenshot 2026-05-12 at 01 13 05" src="https://github.com/user-attachments/assets/d3fce0da-ccdc-438d-9cd4-9291d3daaf8f" />
Summary:

Investigation of a phishing-driven Business Email Compromise (BEC) involving Microsoft 365 mailbox compromise, malicious inbox rules, financial fraud, and international wire transfer activity.




Attack Chain

1️⃣ Initial Access — Phishing (T1566)

        Phishing email received from:sabastian@flanaganspensions.co.uk
        Theme:Microsoft/Copilot invitation
        Goal:Credential harvesting via Microsoft-themed login lure
        
        👉 Confirms phishing-based initial access.


2️⃣ Business Email Compromise (BEC)

        Victim mailbox compromised
        
        Attacker monitored:
        - Pension fund discussions
        - Financial approval emails
        - Withdrawal communications
  
        👉 Indicates Microsoft 365 account takeover for financial fraud.


3️⃣ Threat Actor Infrastructure

        Suspicious IPs identified:
        159.203.17.81
        95.181.232.30

Evidence source:

        Import-Csv .\azure-export-audit-diff.csv

        👉 External IPs tied to mailbox access and inbox rule creation.


4️⃣ Malicious Inbox Rules (Persistence / Concealment)

        Operation observed:
        New-InboxRule
        
Attacker-created hidden folder:

        History
        
Keyword monitored by attacker:

        Withdrawal
        
        👉 Used to automatically hide or process financial emails.


5️⃣ Financial Fraud Activity

        Fraudulent pension withdrawal request identified
        
Transfer destination:

        First Bank of Nigeria PLC
        
SWIFT/BIC observed:

        FBNINGLA
        
        👉 Confirms international wire fraud attempt.


Key Findings:

        Phishing-based credential theft
        Microsoft 365 mailbox compromise
        Malicious inbox rule creation
        Financial email monitoring
        Hidden mailbox folder creation
        International bank transfer fraud
        External attacker IP activity
        

Verdict:

        True Positive — Business Email Compromise confirmed


Attack Includes:

        Initial Access (Phishing)
        Credential Access
        Mailbox Persistence
        Inbox Rule Abuse
        Financial Fraud
        International Wire Transfer
        

Key Insight
Correlating: 

        Phishing Email → Credential Theft → Mailbox Access → Inbox Rule Creation → Email Concealment → Financial Fraud Attempt

        👉 clearly demonstrates a full BEC attack workflow.


MITRE ATT&CK Mapping:

        T1566 — Phishing
        T1114 — Email Collection
        T1098 — Account Manipulation
        T1078 — Valid Accounts
        T1534 — Internal Spearphishing
        T1657 — Financial Theft


SOC Conclusion:

        Attackers successfully compromised a Microsoft 365 mailbox,
        created malicious inbox rules to hide financial emails,
        and attempted fraudulent pension fund transfers to an external Nigerian bank account.
