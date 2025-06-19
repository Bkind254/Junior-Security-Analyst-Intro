# TryHackMe: SOC Level 2 - Room 2

**Date:** June 18, 2025  
**Room Name:**Pyramid Of Pain

## Key Concepts Learned

# What is Pyramid of pain?

The Pyramid of pain is a model that shows how difficult it is fo an attacker when you detect and block certain indicators. The higher up the pyramid you go, the more damage you do to the attacker's ability to operate.

## Levels of The Pyramid

=== Hash Values - (Trivial for attackers to change)

- Definition: A hash is a unique digital fingerprint of a file (like MD5, SHA-1, SHA-256).
- Example: Antivirus might flag a malware file using it's hash
- Why it's weak: Attackers change one small thing in the file to create new hash

=== IP Addresses - (Easy to change)

-Definition: An IP adress is like the home address of a computer on the internet.

- Example: A malware server's IP can be blacklisted
- Why it's weak: Attackers use Fast Flux to constantly change IPs.

\*\*Fast Flux: A technique where attackers rotate IP addresses quickly to avoid detection.

=== Domain Names - (Still easy to change)

- Definition: A domain name is a website name like badsite.com.
- Example: Attackers use weird domain names or punycode to trick users (e.g., lookalike domains).

\*\*Punycode: A way to use special characters in domain names that look like real ones.

=== Host Artifacts - (Annoying for attackers)

- Definition: Host artifacts are things left behind on a system after an attack, like eg(suspicious filese.g., G_jugk.exe, Registry changes, Odd running processes)
- Why it hurts attackers: These can help defenders recognize how the attack happened, even if tools or IPs change.

=== Network Artifacts - (Also annoying)

- Definition: The are patterns or behaviours seen in networking traffic, such as:,Weird URLs , Unusual HTTP requests , Stranger USer-Agents(what software the attacker pretends to be)

\*\* User-agent: A string in web traffic that says what browser or tool is being used (attackers often fake this)

=== Tools & Methods - (Challenging to change)

- Definition: The specific tools or methods attackers use during an attack(like Cobalt Strike, Mimikatz)
- Detection tools include: SSDeep(fuzzy hushing) , YARA rules(Detects patterns in marlware) , Sigma Rules(detect patterns in logs)

\*\*Fuzzy Hashing: Helps find similar(but not identical) files using tools like SSDeep

=== TTPs - Tactics, Techniques, and Procedures - (Very painful for attackers)

- Definition: These describe how attackers operate, like their habits and playbooks.
- Mapped using: The MITRE ATT&CK framework.
- Example: A threat group using phishing and then stealing data via cloud services.

\*\* MITRE ATT&CK: A globally use knowledge base of attacker behavior and techniques.

## Tools & Techniques Used in the Room

- VirusTotal - Scan files and URLs
- Metadefender, Any.run - Sandboxes to analyze malware
- Wireshark/tshark - Inspect network traffic
- SOC Prime, YARA,Sigma - Detection rule platforms.
- MITRE ATT&CK - For tracking attacker behaviour.

## Biggest Takeaway

The higher up the pyramid you go, the harder it is for attackers to recover.  
Focus on identifying behaviour and patterns (TTPs) rather than simple indicators like hashes or IPs.
