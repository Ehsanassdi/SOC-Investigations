BTLO – Piggy Investigation (PCAP Network Traffic Analysis)
<img width="834" height="746" alt="Screenshot 2026-03-11 at 16 37 50" src="https://github.com/user-attachments/assets/c3a29dc3-3abf-4353-908e-b7101dd41a04" />

In this investigation I analysed several PCAP files from the Blue Team Labs Online Piggy challenge using Wireshark. During the analysis, suspicious network activity was identified between an internal host and external infrastructure.



Attack Identified:

    Two main malicious behaviors were detected:
    
    CryptoMiner activity (resource hijacking)
    
    DNS tunneling used for Command & Control (C2)

Indicators included long random DNS subdomains, multiple TXT queries, and repeated DNS communication from the infected host.



Attacker Goal:

    The attacker’s objective was likely to:
    
    maintain Command & Control communication
    
    use the infected machine for cryptocurrency mining
    
    potentially exfiltrate data using DNS tunneling.

    

Tools Used:

    Wireshark
    
    VirusTotal
    
    AbuseIPDB



Result:

The activity was classified as a True Positive and would be escalated to SOC Level 2 for further investigation and containment.
