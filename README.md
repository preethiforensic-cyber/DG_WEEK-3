# DG_WEEK-3


DG Interns Hub - Week 3

Topic: Linux Logs, Sysmon, auditd and Snort Setup
Deadline: 6 November 2026, 11:59 pm


1. Goal of the week

Go deeper into endpoint data with Sysmon (Windows) and auditd (Linux), set up Snort as an intrusion detection system, write detection rules and map them to MITRE ATT&CK.


2. Folder structure

DG Interns HUB
|-- Week 3
    |-- Notes/            10 theory answers, one file per question
    |-- Writeups/         10 lab writeups (4 TryHackMe + 6 LetsDefend)
    |-- Findings/         Hands-on documentation and screenshots
    |-- Cheat Sheet/      Event ID / Rule cheat sheet (29 entries)
    |-- Snort Rules/      local.rules (starter rules + T1046 + optional T1110)
    |-- Week3_Report.pdf
    |-- Week3_Presentation.pptx
    |-- README.md

3. Theory notes (Notes folder)

File	Question
Q01_EDR_and_Endpoint_Data	EDR, why endpoint data matters, EDR vs antivirus
Q02_Sysmon_vs_Windows_Event_Logs	Sysmon, comparison with Windows logs, Event ID table
Q03_auditd_vs_syslog	auditd, how it works, auditd vs syslog
Q04_Snort_IDS_vs_IPS	How Snort works, IDS vs IPS, when to use each
Q05_Snort_Rule_Structure	Rule header and options, common options table
Q06_Signature_vs_Anomaly_Detection	Signature-based vs anomaly-based detection
Q07_MITRE_T1046_Network_Service_Discovery	T1046 and mapping Snort rules to MITRE
Q08_Windows_Event_Log_vs_Sysmon_vs_auditd	Three-way comparison table
Q09_Key_Linux_Log_Files	Key Linux logs table
Q10_Log_Ingestion_and_SIEM_Flow	Log ingestion, Wazuh/Splunk, source-to-dashboard flow

4. Lab writeups (Writeups folder)

TryHackMe (free rooms): Linux Logging for SOC, Intro to Logs, Intro to Log Analysis, Snort.


LetsDefend (free lessons and courses): How to Investigate a SIEM Alert, Security Solutions, Network Log Analysis, SIEM 101, Incident Management, Incident Response on Linux.


5. Hands-on tasks (Findings folder)

Task	File	Result
Install Sysmon with SwiftOnSecurity config	01_Sysmon_Installation	Sysmon installed; Operational log verified
Make events and find them	02_Sysmon_Events	Event ID 1 (PowerShell, user creation), 3 (network), 11 (file create) documented
Explore auditd	03_auditd_Linux_Auditing	auditd installed; command found with ausearch; fields documented
Set up Snort and starter rules	04_Snort_Setup	HOME_NET and EXTERNAL_NET configured; 3 starter rules added
Test starter rules	05_Snort_Alerts_ICMP_SSH_HTTP	Alerts for ping, SSH and HTTP
Nmap SYN scan rule (T1046)	06_Snort_T1046_Nmap_SYN_Scan	nmap -sS triggers SID 1000004
Cheat sheet	Cheat Sheet folder	29 entries

Screenshot file names are listed in Findings/00_Screenshot_Checklist.md.


6. Snort rules (Snort Rules folder)

SID	Message	Purpose
1000001	ICMP Ping Detected	Ping reconnaissance
1000002	SSH Connection Attempt	SSH monitoring
1000003	HTTP Traffic	Web traffic monitoring
1000004	MITRE T1046 - Nmap SYN Port Scan Detected	Port scan detection (T1046)
1000005	MITRE T1110 - SSH Brute Force Attempt Detected	Optional extension (T1110)

7. Key learnings


Sysmon and auditd provide command-line, user, parent-process and network context that default OS logs lack.

Snort alerts are most useful when tagged with MITRE ATT&CK techniques through msg, metadata and reference.

Endpoint and network telemetry answer different questions; a SIEM combines them.

Tuning (Sysmon config, audit rules, Snort thresholds) is what makes detections practical.


8. Tools used (all free)

Sysmon, Windows Event Viewer, auditd (ausearch, aureport), Snort, Nmap, Kali Linux, Ubuntu VM, Windows VM, VirtualBox, TryHackMe, LetsDefend.


