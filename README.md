<h1>Azure VM Honeypot | Microsoft Sentinel 'SIEM'</h1>

<h2>Description</h2>
This project involves configuring a honeypot on a Microsoft Azure virtual machine to generate failed Remote Desktop Protocol 'RDP' login event logs and utilizing Microsoft Sentinel to visualize and map the login attempts geogprahically. 
<br />

<h2>Technologies & Utilities Used</h2>

- <b>IP Gealocation API</b>
- <b>Microsoft Azure Log Analytics workspaces</b>
- <b>Microsoft Defender for Cloud</b>
- <b>Microsoft Sentinel</b>
- <b>Windows Event Viewer</b>
- <b>Windows PowerShell ISE</b>

<h2>Operating Systems Used</h2>

- <b>Windows 10 Professional</b> (21H2)

<h2>Prerequisites</h2>

- <b>Microsoft Azure Free Trial Account</b>
- <b>Windows 10 Professional Microsoft Azure VM 'Default Configuration'</b>

<h3 align="center">Create Microsoft Azure Windows 10 Professional Honeypot VM</h3>
<p align="center">
Azure Windows 10 Professional VM gets created with  the name 'HoneyPot'. <br/>
<img src="https://i.imgur.com/fRxerOk.png" height="80%" width="80%" alt="Create VM"/>
<br />
Choose 'Advanced' under 'NIC network security group' to create a custom inbound security rule. <br/>
<img src="https://i.imgur.com/7a3uB7A.png" height="80%" width="80%" alt="Create VM NIC Security Group Advanced"/>
<br />
Configure an inbound security rule to allow connections to and from any IP address via all ports and any protocol. This is what turns the VM into a honeypot, as it will attract adversaries on the internet to attempt to gain access. <br/>
<img src="https://i.imgur.com/jz7k0kr.png" height="100%" width="100%" alt="Create VM Newtwork Security Group"/>
<br />
</p>

<h3 align="center">Create & Configure Log Analytics workspace</h3>
<p align="center">
Naming and creating the Log Analytics workspace instance. The Log Analytics workspace will be utilized to ingest the failed RDP logins log data from the honeypot VM.<br/>
<img src="https://i.imgur.com/eTTEBP5.png" height="80%" width="80%" alt="Create Log Analytics workspace"/>
<br />
Enable Micorsoft Defender for Cloud with the the Log Analytics workspace in order to gather logs from the honeypot VM. <br/>
<img src="https://i.imgur.com/7s5dRFM.png" height="80%" width="80%" alt="Microsoft Defender for Cloud Enable Plan"/>
<br />
Turn on 'All Events' data collection for Windows security events generated on the honeypot VM. <br/>
<img src="https://i.imgur.com/pnjp5FU.png" height="80%" width="80%" alt="Microsoft Denfender for Cloud Enable Data Collection"/>
<br />
Connecting the honeyot VM to Log Analytics workspace. <br/>
<img src="https://i.imgur.com/88EPqL7.png" height="80%" width="80%" alt="Connect VM to Log Analytics workspace"/>
<br />
Lastly, Microsoft Sentinel is connected to the Log Analytics workspace to visualize the RDP failed login data collected within it. <br/>
<img src="https://i.imgur.com/oJt930C.png" height="100%" width="100%" alt="Add Microsoft Sentinel to Log Analytics workspace"/>
<br />
</p>
