BTLO — Hidden Comrade Investigation
<img width="923" height="763" alt="Screenshot 2026-05-05 at 01 17 56" src="https://github.com/user-attachments/assets/1d0f7f12-98bd-4318-8835-18afeaa268ab" />
Summary:
Investigation of a phishing-based compromise leading to malware execution, persistence via COM hijacking, credential theft, and data exfiltration.

Attack Chain:

1️⃣ Initial Access — Phishing (T1566)

        User visited:
        https://ambitious-beach-044c1211e6.azurestaticapps.net/
        
        Fake “Free AV Scan” page
        👉 Confirms phishing interaction

      
2️⃣ Execution — User Interaction

        Malicious file downloaded:
        scanresults.pdf
        User opened file (Recent files evidence)
              
        👉 Script-based execution triggered from PDF (JavaScript)
        

3️⃣ Malware Delivery — LOLBin Abuse

        Tool used:
          bitsadmin
        Process observed:
          BackgroundTransferHost.exe
        
        👉 Living-Off-The-Land technique used to download payload


4️⃣ Secondary Payload

        File dropped:
          C:\programdata\edge.sct
        
        👉 Scriptlet used for further execution
        

5️⃣ Persistence — COM Hijacking (T1546.015)

        Registry key created:
          HKCU\Software\Classes\TypeLib\{0C2B8070-7731-4F34-81B7-44FE77795223}\1.0\0\win64
        Payload reference:
          script:C:\programdata\edge.sct
        
        👉 Malware hijacks COM object for persistence


6️⃣ Execution Trigger

        Process:
          msedge.exe
        
        👉 Edge loads malicious COM object → executes payload
        

7️⃣ Data Exfiltration

        Destination:
          http://edge.telemetryservices.com
        
        👉 Data sent via HTTP POST


8️⃣ Credential Theft

        Source:
          Edge Login Data database
        Compromised account:
          smartinez@tempestasenergy.com
        
        👉 Browser-stored credentials exposed


9️⃣ Decrypted Discord Password

          isuethispasswordforeverything!
        
        👉 Extracted via AES-GCM decryption of browser credentials
        

Key Findings

        Phishing attack confirmed
        LOLBin abuse (bitsadmin) for payload delivery
        COM Hijacking persistence (T1546.015)
        Script-based execution via PDF + SCT
        Data exfiltration over HTTP
        Credential theft from browser storage
        Password reuse risk identified

        
Verdict

        True Positive — Full compromise confirmed
        

Attack includes:

        Initial Access (Phishing)
        Execution (User + Script)
        Persistence (COM Hijacking)
        Exfiltration
        Credential Theft

        
Key Insight

Correlating:

        Phishing → PDF → bitsadmin → SCT → COM Hijack → Edge execution → Exfiltration → Credential theft

clearly shows a complete attacker kill chain.


MITRE ATT&CK Mapping

        - T1566 — Phishing
        - T1204 — User Execution
        - T1105 — Ingress Tool Transfer
        - T1546.015 — COM Hijacking
        - T1041 — Exfiltration
        - T1555 — Credential Access
