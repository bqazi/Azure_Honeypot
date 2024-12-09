Azure Honeypot: Real-World Cyber Attacks
![Overview](https://github.com/bqazi/Azure_Honeypot/blob/main/images/outline.png) <br><br>

# Overview
The objective of this project was to set up a live virtual machine that acts as a honeypot to attract and analyze cyber attacks. 
This is demonstrated by setting up a Security Information and Event Management (SIEM) system with Microsoft Azure. 

# Tools
* Microsoft Azure (Virtual Machine, Log Analytics Workspace, and Sentinel)
* ipgeolocation.io (API for IP address Geolocation)
* Remote Desktop Connection
* PowerShell ISE

# Implementation
A virtual machine (VM) is set up in Azure with public exposure to the internet. It’s intentionally insecure to attract RDP Brute Force attackers from all around the world. 
Log Analytics Workspace is initialized to collect log data, which is then connected to the VM.

Microsoft Defender for Cloud is enabled to allow gathering logs from the VM in order to be collected by the Log Analytics Workspace.
In addition, Microsoft Sentinel is used to query incident data and build attack maps in a visually representative way.

Using remote access on the local machine to access the VM’s operating system (Windows 10), the PowerShell script (in this repository) is run. It is designed to perform the following:
* Collect failed RDP attack logs from the Windows Event Viewer 
* Use third-party API to collect the attacker’s geolocation
* Outputs a log file to the local machine with the data
As the script is run, the attack logs begin to show and the data is collected.

# Results
After 12 hours of observation, the following map shows the number of attacks:
![12 hours post script](https://github.com/bqazi/Azure_Honeypot/blob/main/images/RDP_map.png) <br><br>

After 24 hours of observation, the primary attacks shifted geographically and at a higher rate:
![24 hours post script](https://github.com/bqazi/Azure_Honeypot/blob/main/images/RDP_map_24.png) <br><br>

The data helps to show patterns, frequency, and distribution of attacks from around the world. This highlights the importance of good security practices. 
Attackers are attempting to breach networks from any place and at any time. It’s crucial to implement best practices in your specific infrastructure with 
frameworks such as NIST, PCI-DSS, and ISO 27001/27002.
