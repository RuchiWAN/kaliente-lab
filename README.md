# kaliente-lab
Cybersecurity Home Lab
Home lab purpose: 
- SIEM -  Security information and event management
- malware analysis;
- DFIR - Digital Forensics and Incident Response;
- OSINT - Open Source Intelligence;
- Vulnerability Scanning;
- Email Forensic;

“Small” list of tools:

Firewall
Malware Analysis (MA) VMs (one for Linux and one for Windows)
Windows 7 host
Windows 10 host
Windows Server AD
Linux Server(s)
Kali Linux
Linux Tsurugi
SIEM
Vulnerability Scanner

VLANs topology:
VLAN 1: management VLAN to access a firewall web GUI.
VLAN 10: corporate WAN VLAN (or Fake WAN). This VLAN includes Kali Linux which will simulate a malicious device coming from outside. Plus it will have access only to corporate VLAN 20. I don’t want to be able to reach the real Internet or my personal machine, as I don’t want to push some malicious script/software by accident to others.
VLAN 20: Corporate LAN network. This is where I will put my servers and end devices (Windows 7 and Windows 10 for example). This VLAN should have access only to the fake internet network.
VLAN 50: This will be my security VLAN that will contain VMs for DFIR(Linux Tsurugi), OSINT, and others. This will simulate a security team network that will have network permission to reach the corporate network (but not the other way around) in order to retrieve logs, files, emails, etc. Also, this network will have access to the real internet, so we can use public tools for analysis (VirusTotal, Talos, MXToolbox…) and perform tools installation and upgrade.
VLAN 99: This will be my isolated LAN network which will contain VMs for malware analysis. This is needed so we can perform both static and dynamic malware analysis without a risk of getting infected any other machine (like my physical device for example).
