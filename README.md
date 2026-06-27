 
<h1> NTFS MFT Forensics Investigation </h1>

<h2>Description</h2>
This project demonstrates a forensic investigation of a Windows NTFS Master File Table (MFT). The objective was to identify suspicious files, determine how they arrived on the endpoint, establish a timeline of actvitiy, and identify the attacker's objective using forensic artifacts.
<br />


<h2> Tools Used 🛠 </h2>

- <b>Windows VM</b> 
- <b>EZ Tools</b>
- <b>Graphical $MFT Viewer</b> 
- <b>Powershell</b>
- <b>MITRE ATT&CK Framework<b>

<h2> Skills Demonstrated </h2>

- <b>Digital Forensics</b> 

- <b>NTFS File System Analysis</b>

- <b>MFT Parsing</b> 

- <b>Timeline, Malware, and Powershell Analysis</b>
- <b>Threat Hunting</b> 
- <b>MITRE ATT&CK Mapping</b>


<h2>Project Walk-Through: </h2>

<p align="center">
Evidence Identification: <br/>
  
<img src="https://github.com/user-attachments/assets/e708a5bd-37df-4681-81a8-64b721df6588"/>

*Figure 1. Opened the challenge files and located Windows $MFT for analysis.*

<br />
<br />
<p align="center">
MFT Parsing:  <br/>
  
<img width="1044" height="653" alt="Screen after parsing file" src="https://github.com/user-attachments/assets/9fd5ce41-3a47-460d-b5b6-c83b43fb2da9"/>

*Figure 2. Used EZ Tools Graphical MFT Viewer to parse and examine the Master File Table.*

<br />
<br />
<p align="center">
Suspicious File Discovery🕵🏾‍♀️: <br/>

<img src="https://github.com/user-attachments/assets/fe98bb67-050d-4395-b391-86e331904279"/>


*Figure 3. Located a suspicious file archive 'scanner98.zip', this stood out because compressed files are commonly used to deliver malware payloads.*

<br />
<br />
<p align="center">
Download Investigation:  <br/>
  
<img src="https://github.com/user-attachments/assets/0ada638b-9682-4819-8089-fbe12413b2ba"/>


*Figure 4. Located the download metadata using the MoTW information stored within the forensic artifacts.*

<br />
<br />
<p align="center">
Timeline Analysis: <br/>
  
<img src="https://github.com/user-attachments/assets/fe98bb67-050d-4395-b391-86e331904279"/>

*Figure 5. Used the 'SI_Created On' timestamp with the SI attribute to determine when the file was downloaded.*

<br />
<br />
<p align="center">
PowerShell Investigation:  <br/>
  
<img src="https://github.com/user-attachments/assets/17a8b332-0bdb-41ab-8f81-e1253397b776"/>


*Figure 6. Investigated a suspicious PowerShell script and found the download source, GitHub hosted payload, and use of Invoke-Expression (IEX) to execute remote code.*

<br />
<br />
<p align="center">
Threat Identification: <br/>

<img src="https://github.com/user-attachments/assets/397c01d9-2944-4166-ae55-b81b004d4a89" />


*Figure 7. The PowerShell script referenced a payload associated with keylogging. Verification against the MITRE ATT&CK Framework idenified: T1056.001-Keylogging*

<br />
<br />

<h2> Findings 📄 </h2>

This investigation traced the full attack chain, identifying the initial malicious ZIP file download, the original download source and timestamp, the remote PowerShell execution, a GitHub hosted payload, the use of the IEX command, and the attacker's keylogging objective. The activity was then mapped to the MITRE ATT&CK framework under T1056.001-Keylogging. Through this project, I strengthened my understanding of Windows forensic artifacts, NTFS MFT analysis, and the importance of mapping observed attacker behavior to the MITRE ATT&CK framework to better kunderstand tactics and techniques used during an incident.

<br />



<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
